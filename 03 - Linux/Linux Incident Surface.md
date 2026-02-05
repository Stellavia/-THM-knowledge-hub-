🔗 [Link to the Room](https://tryhackme.com/room/linuxincidentsurface)

## 🏷️ **Topic:** Explore various areas of Incident Surface in Linux and how to identify the footprints of the incident.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Lab Connection

---
><details><summary>❓Connect with the lab. How many files and folders are in the /home/activities/processes directory?</summary>3</details>
---

## Linux Incident Surface - An Overview

<!-- NO QUESTIONS HERE -->

## Processes and Network Communication

---
><details><summary>❓What is the remote IP to which the process netcom establishes the connection?</summary>68.53.23.246</details>
---
><details><summary>❓Update the osquery command. What is the remote port the netcom process is communicating to?</summary>443</details>
---

## Persistence

---
><details><summary>❓What is the default path that contains all the installed services in Linux?</summary>/etc/systemd/system</details>
---
><details><summary>❓Which suspicious service was found to be running on the host?</summary>benign.service</details>
---
><details><summary>❓What process does this service point to?</summary>benign</details>
---
><details><summary>❓Before getting this service stopped on 11th Sept, how many log entries were observed in the journalctl against this service?</summary>7</details>
---

## Footprints on Disk

---
><details><summary>❓Create a suspicious Debian package on the disk by following the steps mentioned in the task. How many log entries are observed in the dpkg.log file associated with this installation acitvity?</summary>6</details>
---
><details><summary>❓What package was installed on the system on the 17th of September, 2024?</summary>c2comm</details>
---

## Linux Logs

---
><details><summary>❓Examine the auth.log files. Which user attempted to connect with SSH on 11th Sept 2024?</summary>saqib</details>
---
><details><summary>❓From which IP was this failed SSH connection attempt made?</summary>10.11.75.247</details>
---
