🔗 [Link to the Room](https://tryhackme.com/room/windowsmemoryanduseractivity)

## 🏷️ **Topic:** Trace user behavior, command execution, file access, and macro-based payload delivery from memory.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

## Scenario Information

<!-- NO QUESTIONS HERE -->

## Environment & Setup

<!-- NO QUESTIONS HERE -->

## Tracking Sessions

---
><details><summary>❓Which plugin should be used to identify user login sessions from memory?</summary>windows.sessions</details>
---
><details><summary>❓Which user was logged into a console session when WINWORD>EXE and updater.exe were executed?</summary>DESKTOP-3NMNM0H/operator</details>
---
><details><summary>❓According to the UserAssist data, which executable related to command-line activity was launched via a shortcut?</summary>cmd.exe</details>
---
><details><summary>❓Which Volatility 3 plugin reveals evidence of programs launched by a user through the graphical interface?</summary>windows.registry.userassist</details>
---

## Command Execution & File Access

---
><details><summary>❓What file was passed to WINWORD.EXE</summary>cv-resume-test.docm</details>
---
><details><summary>❓What is the name of the Volatility 3 plugin that extracts open files, registry keys, and kernel objects from process handle tables?</summary>windows.handles</details>
---
><details><summary>❓What is the full device path where the.docm file was found open in WINWORD.EXE's memory space?</summary></details>

<!-- DOPLNIT ODPOVED -->

---
><details><summary>❓What Windows command-line switch was used to open WINWORD.EXE in a new instance?</summary>/n</details>
---

## Tracing User Execution

><details><summary>❓What command did we use to confirm that the dumped .dat file is a Microsoft Word document?</summary>file</details>
---
><details><summary>❓According to the `olevba` output, what is the name of the file downloaded and executed by the macro?</summary>pdfupdater.exe</details>
---
><details><summary>❓What is the full URL hardcoded in the macro for downloading the executable?</summary></details>
---
