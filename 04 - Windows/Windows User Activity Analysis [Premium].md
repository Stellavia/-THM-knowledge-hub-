🔗 [Link to the Room](https://tryhackme.com/room/windowsuseractivity)

## 🏷️ **Topic:** What happened in those 36 hours? A forensics case to solve.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Lab Connection

---
><details><summary>❓Connect with the lab. How many tools/folders are in the EZ tools folder on the Desktop?</summary>12</details>
---

## Revisiting Registry

---
><details><summary>❓Which Hive stores information about installed software?</summary>SOFTWARE</details>
---
><details><summary>❓What is the current size of the SAM Hive in the attached lab? (in KB)</summary>128</details>
---

## Performing Registry Forensics

---
><details><summary>❓The suspect typed a suspicious path in the Windows Explorer, that points to a tmp directory in C drive. What is the full path?</summary>C:\system\home\tmp</details>
---
><details><summary>❓In the WorldWheelQuery search, what was the latest term searched by the user?</summary>wipe</details>
---
><details><summary>❓Where was the last text file saved by the suspect?</summary>C:\system\home\tmp\code.txt</details>
---
><details><summary>❓From the Hacking-tools folder, which suspicious key logging tool was executed 5 times?</summary>keylogger.exe</details>
---
><details><summary>❓Which Disk Wiping utility was executed on this host?</summary>DiskWipe.exe</details>
---

## ShellBags: Navigating the Past

---
><details><summary>❓What is the IP address of the Network Share, where the user accessed three folders?</summary>10.10.17.228</details>
---
><details><summary>❓What is the name of the second sub-folder within the Documents folder of the network share that the user accessed?</summary>secret-doc</details>
---

## LNK Files - Shortcut

---
><details><summary>❓What is the document that was last opened by the user on this machine?</summary>10_ways_to_Exfiltrate_Data.pdf</details>
---
><details><summary>❓Analyzing the code.Ink file shows that it was accessed from the network shared drive. What is the full path of the network directory?</summary>\\10.10.17.228\Users\Administrator\Documents\secret-documents</details>
---

## JumpList: Leap Through Time

---
><details><summary>❓A text file named code.txt was accessed from a tmp directory. What is the full path of the tmp directory?</summary>C:\system\home\tmp\code.txt</details>
---
><details><summary>❓What URL was accessed using Internet Explorer?</summary>http://10.10.17.228/</details>
---
><details><summary>❓When did the user access the “How to Hack.pdf” file?</summary>2024-03-04 12:28:26</details>
---
