🔗 [Link to the Room](https://tryhackme.com/room/windowsmemoryandprocs)

## 🏷️ **Topic:** Analyze a memory dump of a Windows host and uncover malicious processes. ##

# 📚 Study Notes #

- Malware can run only in memory, so memory analysis is an important forensic skill.
- Tools like Volatility and Redline help extract data, but analysts must interpret and connect the findings themselves.

## Learning Objectives ##

- This room focuses on analyzing a Windows memory dump to identify processes, investigate attacks, and report results.

## Scenario ##

- You are part of an incident response team investigating a possible compromise at TryHatMe, an online hat store.
- A full memory dump of a Windows host was already collected, and this case represents your first real investigation with guidance from a senior analyst.
- The incident (THM-0001) was escalated on May 5th, 2025, after a potentially compromised Windows system (WIN-001) was identified.
- A full memory dump was taken to preserve evidence, including host details, timestamp, and hash to ensure integrity.

<img width="5084" height="3320" alt="image" src="https://github.com/user-attachments/assets/3aea08b2-e4e5-49b1-9a8b-6f3059c35a10" />

## Windows Process Architecture ##

- When you open a program, Windows builds a few internal “records” so it can keep track of what the program is doing in memory.

- Windows uses four core structures (important pieces): EPROCESS, ETHREAD, PEB, and TEB.
  - EPROCESS: is Windows’ main file for a program. It tells the system: this program exists, here’s its ID, and here are its threads. It exists in kernel space.
  - ETHREAD: represents a single task inside the program. A program can have many threads, and each one does part of the work. It also exists in kernel space.
  - PEB [Process Environment Block]: is the program’s settings and startup info. It stores things like command-line arguments and loaded DLLs. PEB exists in user space.
  - TEB [Thread Environment Block]: is the personal notebook for each thread. It keeps thread-specific data like stack info and thread-local storage. It also exists in user space. 

- When a program starts, Windows creates all four structures as they are linked together with pointers, so Windows can jump between them easily.

### 📌 Memory preparation process explained ###

1. Memory is prepared for the program itself (EXE), the PEB (process info) and the TEB (thread info). Basically this means that before a program can run, Windows needs to set up space in RAM and organize it. Think of it like setting up a desk before you start working.
- Windows loads the program file (.exe) from disk into RAM. The code and data inside the EXE are mapped into the process’s memory, which means that Windows now knows where the prtogram's code lives, where its data lives and where execution should start.
    = Without this process the CPU has nothing to execute.
2. Windows creates a PEB structure in user space. This stores important process info like cmd arguments, environment variables, loaded DLLs or debugging flags. The program uses this info while running and you probably won't even notice it.
3. Next one is memory for the TEB. Every thread gets its own TEB. Here Windows allocates memory for thread's stack (where function calls and local variables live), thread-local storage (TLS) and error handling data. Without TEB, a thread wouldn't know where its stack is or how to handle errors.
  
📝 Thread is a single line of execution inside a program. A process = the whole program, a THREAD = a worker inside that program doing tasks. 
E.g. Your browser is one process; Loading a webpage, playing a video, responding to clicks = different threads.

- **Only after this setup does the program actually start running.**

- Memory forensic tools rely on these structures to extract process data.

- Understanding these links helps identify malicious or hidden activity.

><details><summary>❓ What field is used to keep track of all the active processes? Only enter the fields' name.</summary>ActiveProcessLinks</details>
***Solution***: *This field inside the EPROCESS structure used to link all currently running processes together in a list. Windows then walks this list to know which processes are active.*
  
><details><summary>❓What field is used to store the PID of a process? Only enter the fields' name. </summary> UniqueProcessId</details>
***Solution***: *It's field inside the EPROCESS structure. Windows uses this value to uniquely identify each running process.*

## Initial Triage of a New Memory Dump ##

  - Within this task you'll analyze a Windows memory dump to find suspicious processes using Volatility 3 on an Ubuntu VM.

  - Steps:
1. Verify the memory dump - check MD5 hash to ensure integrity.
2. Extract processes using Volatility - `windows.pslist` (active processes), `windows.psscan` (all processes, including terminated/unlinked), `windows.pstree` (processes with parent-child relationships), `windows.psxview` (cross-checks processes and threads for anomalies)
3. Analyze process output - look for suspicious names, paths, or masquerading processes (e.g., `scvhost.exe`, `dockerupdater.exe`) and compare extracted processes to a baseline to identify unusual or unexpected processes.
4 . Remove false positives (legitimate processes missing from baseline, truncated names, etc.)

- Now you have to investigate links between suspicious processes and other processes to uncover hidden malicious activity.

><details><summary>❓What is the PID of the csrss.exe process that has 12 threads? You can use the pslist.txt file to find the answer. </summary>440</details>
***Solution***: *The `pslist.txt` contains the output of Volatility's `Windows.pslist` module, which looks like a table. Search for `csrss.exe` in it. Search for the one that has 12 threads as Windows can have several csrss.exe threads running.*
  
><details><summary>❓What is the (memory) Offset(V) of the process with PID 5672? You can use the pslist.txt file to find the answer. </summary>0x990b29293080 </details>
***Solution***: *In the `pslist.txt`* search for PID 5672 and look at the Offset(V) column, there's your answer.


## Linking Processes ##

- Before analyzing suspicious processes in detail, check if they are connected to other processes.

- Malware often runs as a chain of processes, where one process spawns another to carry out malicious activity.

e.g.: 
```explorer.exe → cmd.exe → powershell.exe → svchost.exe → asyncrat.exe```
A malicious LNK file triggers cmd.exe, which starts PowerShell to download the payload, svchost.exe is used to masquerade as a system process, and finally the malware (asyncrat.exe) runs.

>[!NOTE]
> The processtree.txt file maps parent-child process relationships and can be searched by PID to identify the process name.
>
### Task ###

1. Generate a process tree using Volatility: `vol3 -f memory_dump windows.pstree > processtree.txt`
2. Simplify the tree to show PID, PPID, and ImageFileName: `cut -d$'\t' -f1,2,3 processtree.txt`

<img width="437" height="219" alt="image" src="https://github.com/user-attachments/assets/9a320d27-3280-4d58-ba94-a6ab560c6697" />

<img width="515" height="504" alt="image" src="https://github.com/user-attachments/assets/4dd3ba48-f2e0-4c4e-8b4b-9d9f633e141e" />

### Key Observations ###
- Multiple "update” processes are chained unusually, suggesting suspicious activity.
- Presence of conhost.exe indicates possible network activity.
- The chain is highly likely malicious based on process names, hierarchy, and behavior.

><details><summary>❓What is the parentID (PPID) of the services.exe (PID 664) process? Use the processtree.txt file to answer the question. </summary>524</details>

><details><summary>❓What is the ImageFileName of the process that has the PID 7788? Use the processtree.txt file to answer the question. </summary>FTK Imager.exe</details>
***Solution***: *`processtree.txt` is the output of Volatility's `windows.pstree` module. Use `less processtree.txt` then scroll or use `/7788` to search.*

>[!NOTE]
>*Use `pslist` to see what exists, and `pstree` to see how it happened.
>
> **pslist** - *What is running?* - shows a flat list of processes found in memory; focuses on PID, process name, thread count, memory offset - to identify suspicious process names, find PIDs, threads and offsets and to get an overview of running processes.
>  - e.g. "*What is the PID of* `csrss.exe` *with 12 threads*?" or "*What is the Offset(V) of PID 5672*?"
>    
> **pstree** - *Who spawned whom?* - shows processes in a parent-child tree structure; focuses on process relationships and execution chains - it's best used to reconstruct attack chains, see how malware was launched or identify suspicious parent-child behavior.
>  - e.g. "*Which process started* `powershell.exe`?" or "*What process is associated with PID 7788*?"




><details><summary>❓ </summary></details>
><details><summary>❓ </summary></details>
><details><summary>❓ </summary></details>
><details><summary>❓ </summary></details>
><details><summary>❓ </summary></details>
