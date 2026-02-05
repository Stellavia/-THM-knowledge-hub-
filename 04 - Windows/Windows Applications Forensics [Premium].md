🔗 [Link to the Room](https://tryhackme.com/room/windowsapplications)

## 🏷️ **Topic:** Perform a live analysis on Windows systems, focused on determining the outliers based on known behaviour of scheduled tasks, services, and installed applications.
# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Log Insights: Scheduled Tasks and Services

---
><details><summary>❓Who created the malicious scheduled tasks?</summary>mike.myers</details>
---
><details><summary>❓Based on the ones discovered from the logs, what URL is accessed by this malicious scheduled task? (format: defanged URL)</summary>hxxp[://]hrcbishtek[.]com/a</details>
---
><details><summary>❓Based on the logs, what is the name of the malicious service?</summary>server power</details>
---

## Manual Inspection: Scheduled Tasks

---
><details><summary>❓Aside from the scheduled tasks from Windows Event Logs, what does the second malicious scheduled task execute?</summary>C:\Users\Public\pagefilerpqy.exe</details>
---
><details><summary>❓Based on Q1, what time does the second malicous task execute daily? (format: HH:MM, e.g. 18:30)</summary>17:21</details>
---

## Manual Inspection II: Services

---
><details><summary>❓Aside from the service determined through logs, what is the full path of the binary executed by the second malicious service?</summary>C:\Windows\Temp\aKzjdD.exe</details>
---
><details><summary>❓What is the last write time of the second malicious service? (format: MM/DD/YYYY HH:MM:SS)</summary>03/07/2024 17:53:53</details>
---

## Dissecting Browser Artefacts I: Mozilla Firefox

---
<!-- DOPISAT ODPOVED -->

><details><summary>❓What is the first URL accessed by the user related to the phishing website? (format: defanged URL)</summary></details>
---
><details><summary>❓Based on Q1, what time did the user access this URL in the UTC timezone? (format: MM/DD/YYYY HH:MM:SS)</summary>03/04/2024 20:53:32</details>
---
><details><summary>❓Which O365 cookie containing user session information was seen on the phishing website?</summary>ESTSAUTHPERSISTENT</details>
---

## Dissecting Browser Artefacts II: Google Chrome


<!-- DOPISAT ODPOVED -->

---
><details><summary>❓What URL does the maliciouos Chrome extension report to? (format: defanged URL)</summary></details>
---

## Dissecting Browser Artefacts III: Microsoft Edge

<!-- DOPISAT ODPOVED -->

---
><details><summary>❓What is the first URL the Microsoft Edge user accessed related to the malicious domain? (format: defanged URL)</summary></details>
---

## Deep-diving on Office Applications I: Microsoft Outlook

---
><details><summary>❓What email is used by the phishing email sender?</summary>julianne.westcott@hotmail.com</details>
---

## Deep-diving on Office Applications II: Microsoft Teams


<!-- DOPISAT ODPOVED -->


---
><details><summary>❓What is the file name of the malicious attachment sent via Microsoft Teams?</summary>system_update.zip</details>
---
><details><summary>❓What is URL found inside the malicious attachment? (format: defanged URL)</summary></details>
---

## Deep-diving on Office Applications III: Microsoft OneDrive


<!-- DOPISAT ODPOVED -->


---
><details><summary>❓What is the URL of the usual SharePoint site synced by the user?</summary></details>
---
