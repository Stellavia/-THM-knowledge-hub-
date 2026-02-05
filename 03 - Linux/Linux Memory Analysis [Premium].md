🔗 [Link to the Room](https://tryhackme.com/room/linuxmemoryanalysis)

## 🏷️ **Topic:** Learn how to investigate and find the footprints of a threat actor in the Linux memory.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

## Scenario Information

<!-- NO QUESTIONS HERE -->

## Lab Connection

<!-- NO QUESTIONS HERE -->

## Memory Overview: Linux vs Windows

<!-- NO QUESTIONS HERE -->

## Hunting for Suspicious Process

---
><details><summary>❓What is the MD5 hash of the image we are investigating?</summary>c0fbf40989bda765b8edaa41f72d3ee9</details>
---
><details><summary>❓What is the PID of the suspicious Netcat process?</summary>15011</details>
---
><details><summary>❓What is the name of the suspicious process running from the hidden tmp directory?</summary>.strokes</details>
---
><details><summary>❓What port number was used while setting up a Python server to transfer files?</summary>9090</details>
---
><details><summary>❓A suspicious process with PID 821 was found running on the system. What is the full path of the process?</summary>/home/microservice/printer_app</details>
---

## Hunting for Suspicious Network Activities

---
><details><summary>❓What is the IP address of the remote server, to which a TCP connection was established using python?</summary>10.100.1.125</details>
---
><details><summary>❓What was the IP address of the infected host found in the record?</summary>10.10.163.215</details>
---
><details><summary>❓What is the MAC address of the network interface associated with the infected device?</summary>02:83:88:6b:5a:1f</details>
---
><details><summary>❓What is the port number opened for the reverse shell by the adversary on the infected host?</summary>9898</details>
---

## Hunting for User Activities

---
><details><summary>❓The network team has detected a suspicious attempt to create a new account on the system. Can you investigate and find the name of the backdoor account created?</summary>james</details>
---
><details><summary>❓The bash history shows a suspicious command that established a reverse shell. What is the attacker's IP address?</summary>10.12.14.32</details>
---
