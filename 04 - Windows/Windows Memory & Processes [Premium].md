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

### Memory preparation process explained ###

1. Memory is prepared for the program itself (EXE), the PEB (process info) and the TEB (thread info). Basically this means that before a program can run, Windows needs to set up space in RAM and organize it. Think of it like setting up a desk before you start working.
- Windows loads the program file (.exe) from disk into RAM. The code and data inside the EXE are mapped into the process’s memory, which means that Windows now knows where the prtogram's code lives, where its data lives and where execution should start.
    = Without this process the CPU has nothing to execute.
2. Windows creates a PEB structure in user space. This stores important process info like cmd arguments, environment variables, loaded DLLs or debugging flags. The program uses this info while running and you probably won't even notice it.
3. Next one is memory for the TEB. Every thread gets its own TEB. Here Windows allocates memory for thread's stack (where function calls and local variables live), thread-local storage (TLS) and error handling data. Without TEB, a thread wouldn't know where its stack is or how to handle errors.
  

Only after this setup does the program actually start running.



- Memory for the executable, PEB, and TEB is initialized before execution begins.

Why It Matters

- Memory forensic tools rely on these structures to extract process data.
- Understanding these links helps identify malicious or hidden activity.
