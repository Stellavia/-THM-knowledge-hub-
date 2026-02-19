🔗 [Link to the Room](https://tryhackme.com/room/linuxlogsinvestigations)

## 🏷️ **Topic:** Explore Linux system logs for effective incident response.

1. [Logging Levels and Kernel Logis](#logging-levels-and-kernel-logis)<br>
2. [Exploring the /var/log Directory](#exploring-the-varlog-directory)<br>
3. [User Logging With Syslog](#user-logging-with-syslog)<br>
4. [Journalctl](#journalctl)<br>
5. [Leveraging Auditd for Security](#leveraging-auditd-for-security)<br>
6. [Examining Auth Logs](#examining-auth-logs)<br>
7. [Analysing Application Logs](#analysing-application-logs)<br>
8. [Linux Logs Capstone](#linux-logs-capstone)<br>

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

&nbsp;

## Logging Levels and Kernel Logis

&nbsp;








&nbsp;

---
><details><summary>❓Which type of logs provide messages related to hardware events and system errors?</summary>Kernel</details>
---
><details><summary>❓What is the memory space used to store system messages?</summary>Kernel ring buffer</details>
---
><details><summary>❓What is the degault log level used to inform about non-imminent errors?</summary>WARNING</details>
---

&nbsp;

## Exploring the /var/log Directory

&nbsp;











&nbsp;

---
><details><summary>❓Which log file can be used to record failed login attempts only?</summary>btmp</details>
---

&nbsp;

## User Logging With Syslog

&nbsp;










&nbsp;

---
><details><summary>❓What severity level keyword is used to indicate immediate action is needed in a syslog message?</summary>alert</details>
---
><details><summary>❓What facility code is used for cron jobs?</summary>9</details>
---

&nbsp;

## Journalctl

&nbsp;








&nbsp;

---
><details><summary>❓To configure the persistence of journal logs, which parameter has to be modified within the journald configuration file?</summary>Storage</details>
---

&nbsp;

## Leveraging Auditd for Security

&nbsp;









&nbsp;

---
><details><summary>❓Which utility is used to search for auditd logs?</summary>ausearch</details>
---

&nbsp;

## Examining Auth Logs

&nbsp;













&nbsp;

<!-- DOPLNIT ODPOVED -->

---
><details><summary>❓What command can be used to search logs related to a session opened for a user?</summary></details>
---

&nbsp;

## Analysing Application Logs

&nbsp;










&nbsp;

---
><details><summary>❓Which folder contains Apache2 logs?</summary>/var/log/apache2</details>
---

&nbsp;

## Linux Logs Capstone

&nbsp;











&nbsp;

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

&nbsp;
