🔗 [Link to the Room](https://tryhackme.com/room/linuxliveanalysis)

## 🏷️ Learn how to perform live forensics on a Linux host.


1. [Introduction and Lab connection](#introduction-and-lab-connection)<br>
2. [Live Forensics: An Overview](#live-forensics-an-overview)<br>
3. [Tool of the Trade: Osquery](#tool-of-the-trade-osquery)<br>
4. [System Profiling](#system-profiling)<br>
5. [Hunting for Processes](#hunting-for-processes)<br>
6. [Investigating Network Connections](#investigating-network-connections)<br>
7. [TTP Footprints on Disk](#ttp-footprints-on-disk)<br>
8. [Persistence: Establishing Foothold](#persistence-establishing-foothold)<br>


# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->



&nbsp;

# Introduction and Lab connection

&nbsp;





<!-- NO QUESTIONS HERE -->



&nbsp;

# Live Forensics: An Overview

&nbsp;





<!-- NO QUESTIONS HERE -->

&nbsp;

# Tool of the Trade: Osquery

&nbsp;








&nbsp;

---
><details><summary>❓What hostname is returned after running the following query? Query: select * from etc_hosts where address = `0.0.0.0`;</summary>attacker.thm</details>
---
><details><summary>❓On the official website, how many tables are listed for Linux OS?</summary>154</details>
---

&nbsp;

# System Profiling

&nbsp;








&nbsp;

---
><details><summary>❓What is the Machine ID of the machine we are investigating?</summary>dc7c8ac5c09a4bbfaf3d09d399f10d96</details>
---
><details><summary>❓What is the architecture of the host we are investigating?</summary>x86_64</details>
---

&nbsp;

# Hunting for Processes

&nbsp;








&nbsp;

---
><details><summary>❓What is the name of the process running from the tmp directory? (Note: Not Hidden one)</summary>sshdd</details>
---
><details><summary>❓What is the name of the suspicious process running in the memory of the infected host?</summary>.systm_updater</details>
---
><details><summary>❓What is the name of the process runniing from the user directory?</summary>rdp_updater</details>
---

&nbsp;

# Investigating Network Connections

&nbsp;









&nbsp;

---
><details><summary>❓What is the state of the local port that is listening on port 80?</summary>ESTABLISHED</details>
---

&nbsp;

# TTP Footprints on Disk

&nbsp;







&nbsp;

---
><details><summary>❓Investigate the opened files. What is the opened file associated with the suspicious process running on the system?</summary>keylogger.log</details>
---
><details><summary>❓What is the name of the process that is associated with the suspicious file found in the above question?</summary>sshdd</details>
---
><details><summary>❓What is the name of the hidden binary found in the root directory?</summary>.systmd</details>
---
><details><summary>❓What is the name of the suspicious package installed on the host?</summary>datacollector</details>
---
><details><summary>❓The suspicious package contains a secret code. What is the code hidden in the description?</summary>{***_**_******_*******}</details>
---

&nbsp;

# Persistence: Establishing Foothold

&nbsp;







&nbsp;

---
><details><summary>❓Which suspicious service was observed to be installed on this infected machine using netcat?</summary>systm.service</details>
---
><details><summary>❓What is the full path of the process found in the cron table?</summary>/home/badactor/storage/.secret_docs/rdp_updater</details>
---

&nbsp;
