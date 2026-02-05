🔗 [Link to the Room](https://tryhackme.com/room/linuxlogsinvestigations)

## 🏷️ **Topic:** Explore Linux system logs for effective incident response.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Logging Levels and Kernel Logis

---
><details><summary>❓Which type of logs provide messages related to hardware events and system errors?</summary>Kernel</details>
---
><details><summary>❓What is the memory space used to store system messages?</summary>Kernel ring buffer</details>
---
><details><summary>❓What is the degault log level used to inform about non-imminent errors?</summary>WARNING</details>
---

## Exploring the /var/log Directory

---
><details><summary>❓Which log file can be used to record failed login attempts only?</summary>btmp</details>
---

## User Logging With Syslog

---
><details><summary>❓What severity level keyword is used to indicate immediate action is needed in a syslog message?</summary>alert</details>
---
><details><summary>❓What facility code is used for cron jobs?</summary>9</details>
---

## Journalctl

---
><details><summary>❓To configure the persistence of journal logs, which parameter has to be modified within the journald configuration file?</summary>Storage</details>
---

## Leveraging Auditd for Security

---
><details><summary>❓Which utility is used to search for auditd logs?</summary>ausearch</details>
---

## Examining Auth Logs

<!-- DOPLNIT ODPOVED -->

---
><details><summary>❓What command can be used to search logs related to a session opened for a user?</summary></details>
---

## Analysing Application Logs

---
><details><summary>❓Which folder contains Apache2 logs?</summary>/var/log/apache2</details>
---

## Linux Logs Capstone

---
><details><summary>❓What is the IP address from which the application was exploited?</summary>10.10.190.69</details>
---
><details><summary>❓What file contains the reverse shell?</summary>cmd.php</details>
---
><details><summary>❓At which port was the reverse shell running?</summary>5000</details>
---
><details><summary>❓What is the file name that was being executed with sudo privileges?</summary>tests.sh</details>
---
><details><summary>❓What is the name of the user created using the service?</summary>attacker</details>
---
><details><summary>❓Was the new account ever logged in to? y/n</summary>n</details>
---
