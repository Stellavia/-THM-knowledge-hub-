🔗 [Link to the Room](https://tryhackme.com/room/antireverseengineering)

## 🏷️ **Topic:** Learn the techniques used by malware authors to bypass detection.
# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

<!-- NO QUESTIONS HERE -->

&nbsp;

## Anti-Debugging 

---
><details><summary>❓What is the name of the Windows API function used in a common anti-debugging technique that detects if a debugger is running?</summary>IsDebuggerPresent</details>
---

## Anti-Debugging using Suspend Thread

---
><details><summary>❓What is the Windows API function that enumerates windows on the screen so the malware can check the window name?</summary>EnumWindows</details>
---
><details><summary>❓What is the hex value of a nop instruction?</summary>90</details>
---
><details><summary>❓What is the instruction found at memory location 004011CB?</summary>add esp,8</details>
---

## VM Detection (Overview)

---
><details><summary>❓What is the name of the identifiable process used by malware to check if the machine is running inside VirtualBox?</summary>vboxservice</details>
---
><details><summary>❓What is the OUI automatically assigned specifically to VMware?</summary>00:50:56</details>
---
><details><summary>❓Using Task Manager, what process indicates that the machine for this room is an Amazon EC2 Virtual Machine?</summary>amazon-ssm-agent.exe</details>
---

## VM Detection Checking the Temperature

---
><details><summary>❓In the C code snippet, what is the full WQL query used to get the temperature from the Win32_TemperatureProble class?</summary>SELECT * FROM MSAcpi_ThermalZoneTemperature</details>
---
><details><summary>❓What register holds the memory address that tells the debugger what instruction to execute next?</summary>EIP</details>
---
><details><summary>❓Before uReturn is compared to zero, what is the memory location pointed to by [ebp-4]</summary>0019FF1C</details>
---

## Packers (Overview)

---
><details><summary>❓What is the decoded string of the base64 encoded “VGhpcyBpcyBhIEJBU0U2NCBlbmNvZGVkIHN0cmluZy4=”?</summary>This is a BASE64 encoded string.</details>
---

## Identifying and Unpacking

---
><details><summary>❓According to DetectItEasy, what is the version of the Microsoft Linker used for linking packed.exe?</summary>14.16</details>
---
><details><summary>❓According to pestudio, what is the entropy of the UPX2 section of packed.exe?</summary>2.006</details>
---
