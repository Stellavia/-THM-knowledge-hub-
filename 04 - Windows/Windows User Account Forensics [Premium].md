🔗 [Link to the Room](https://tryhackme.com/room/windowsuseraccountforensics)

## 🏷️ **Topic:**Learn where to search for artefacts associated with users and accounts.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Windows Account Types

---
><details><summary>❓What type of accounts are used by the Windows operating system and various apps?</summary>System and Service Accounts</details>
---
><details><summary>❓What centrally manages local user accounts and domain accounts?</summary>Domain Controller</details>
---

## Account Lifecycle Artefacts

---
><details><summary>❓How many users were found using the DSInternals command?</summary>5</details>
---
><details><summary>❓What is the value of the “bootKey” variable?</summary>36c8d26ec0df8b23ce63bcefa6e2d821</details>
---
><details><summary>❓What is the SID of the domain user, m.ascot?</summary>S-1-5-21-1966530601-3185510712-10604624-1111</details>
---

## Account Authentication Artefacts

---
><details><summary>❓What is the user name used for the NTLM authentication?</summary>admin</details>
---
><details><summary>❓What was the Server Challenge sent to the client during the Challenge stage of the NTLM handshake?</summary>212ba239356b3d82</details>
---
><details><summary>❓What is the Dns Name of the other result from the the DsGetDomainControllerInfo response?</summary>dcfr.lab.lan</details>
---

## Group Policy Artefacts

---
><details><summary>❓What is the name of the user specified as the apply target for this Policy?</summary>Michael Ascot</details>
---
><details><summary>❓Under Computer Configuration > Policies > Administrative Templates > Windows Components > Windows Defender Antivirus > Real-time Protection, what is the setting that was enabled?</summary>Turn off real-time protection</details>
---
><details><summary>❓There is an updated malicious startup PowerShell script. What is the filename of this script? (Without file extension)</summary>superimportant-updated</details>
---
><details><summary>❓What is the IP address of the C2 server the script would exfiltrate to?</summary>192.0.2.123</details>
---
