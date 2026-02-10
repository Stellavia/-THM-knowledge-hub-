🔗 [Link to the Room](https://tryhackme.com/room/macosforensicsbasics)

## 🏷️ Learn the basics to prepare for performing forensics on macOS.

# 📚 Study Notes 

&nbsp;

**== PAGE IN PROGRESS ==**

&nbsp;

<!-- NO QUESTIONS HERE -->

## Introduction

## A Brief History of macOS

---
><details><summary>❓In which year was the APFS file system introduced by Apple?</summary>2017</details>
---
><details><summary>❓Which file system is common amongst all  Apple devices, including iOS, watchOS, and tvOS?</summary>APFS</details>
---

## HFS+ File System

---
><details><summary>❓What is the latest date that the HFS+ file system supports? Format DD/MM/YYYY</summary>06/02/2040</details>
---
><details><summary>❓In the HFS+ file system, which file contains a list of all the files and directories present in the file system?</summary>Catalog file</details>
---

## APFS File System

---
><details><summary>❓In macOS, which command can be used to list all available APFS volumes?</summary>diskutil apfs list</details>
---

## macOs Directory Structure and Domains

---
><details><summary>❓Files in which domain can't be modified even by using sudo privileges?</summary>System</details>
---
><details><summary>❓Which domain is the most forensically important domain from a user activity point of view?</summary>User</details>
---

## macOS File Formats

---
><details><summary>❓Which of the file types discussed above are similar to device drivers in Windows?</summary>.kext files</details>
---

## Challenges in Data Acquisition

---
><details><summary>❓Which command can be used to disable SIP?</summary>csrutil disable</details>

## Mounting APFS Disk Image

---
><details><summary>❓In the disk image provided in the attached VM, what is the UUID of the volume containing user data?</summary></details>
---
><details><summary>❓What is the name of the user who used this Mac device?</summary>thm</details>
---
><details><summary>❓There is a text file in the User directory of the above-mentioned user. What is the name of this file?</summary>creds.txt</details>
---
><details><summary>❓It looks like the file contains credentials for different users and their passwords. What is the password of the user we identified above?</summary>12345</details>
---
