🔗 [Link to the Room](https://tryhackme.com/room/androidanalysis)

## 🏷️ **Topic:** Dive deep into the Android OS and learn how to examine from a forensics point of view.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

## Lab Connection

<!-- NO QUESTIONS HERE -->

## Android Architecture - An Overview

---
><details><summary>❓Navigate the directories in FTK Imager. Examine the build.prop file found in the system folder. What is the device's serial number?</summary>ABC123456789</details>
---

## Android - Frensics Artifacts

---
><details><summary>❓Examine the artifact containing information about the device's installed apps. What is the last package installed on this device?</summary>com.sneakcam.capture</details>
---

## Tools for the Trade

<!-- NO QUESTIONS HERE -->

## Unboxing the Artifacts

---
><details><summary>❓What is the flag hidden inside SMS?</summary>FLAG{***_******_******}</details>
---
><details><summary>❓In the call logs, which number has the longest call duration?</summary>+14155550011</details>
---
><details><summary>❓What is the second-to-last suspicious contact name in the list?</summary>Encrypted User</details>
---
><details><summary>❓Most Chrome searches indicate that the user was looking for sites to upload data. What is the last URL found in the list for a similar purpose?</summary>https://easyupload.io</details>
---
><details><summary>❓What is the name of the Bluetooth device found in the configuration?</summary>Pixel_6_User</details>
---

## Triaging with ALEAPP

---
><details><summary>❓What is the name of the package found that could be used for the data exfiltration?</summary>com.data.exfiltool</details>
---
><details><summary>❓One of the MMS message indicates the website used to send the sensitive file? What is the name of that site?</summary>MediaFire</details>
---
><details><summary>❓In the contacts, what is the email address associated with the suspicious user named "Encrypted User"?</summary>ghost123@tutanota.com</details>
---
><details><summary>❓A sensitive PDF document was found on the device. Examine the document in the downloads folder. What is the flag hidden inside it?</summary>FLAG{*******_******_****}</details>
---

## Framing Questions

<!-- NO QUESTIONS HERE -->
