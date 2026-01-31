🔗 [Link to the Room](https://tryhackme.com/room/operatingsystemsecurity)

## 🏷️ **Topic:** This room introduces users to operating system security and demonstrates SSH authentication on Linux. ##

# 📚 Study Notes #

## Intro to Operating System Security ##

- An operating system (OS) is what makes a computer or phone usable. Hardware (CPU, memory, keyboard, screen, storage) can’t do anything on its own — the OS controls it and lets apps run.
- Apps like browsers, messaging apps, and email cannot talk directly to hardware. They must go through the operating system, which sets the rules.

- Different devices use different operating systems:
  - Computers: Windows, macOS, Linux
  - Phones: Android, iOS
  - Servers: Windows Server, Linux, Solaris, AIX
  
- Devices store very sensitive data (messages and photos, e-mails, passwords, banking apps, work or school files) and because of this, the operating system must be secured.

- Operating system security protects three key things which are the foundation of OS security:
  - **Confidentiality**: Only authorized people can see your data
  - **Integrity**: Data cannot be changed or tampered with
  - **Availability**: Your system is usable when you need it


><details><summary>❓Which of the following is not an operating system? AIX, Android, Chrome OS, Solaris, Thunderbird</summary>Thunderbird</details>
Solution: It's an e-mail client application.

## Common Examples of OS Security ##

- Operating system security protects confidentiality (who can see data), integrity (data can’t be changed) and availability (system is usable)

- Attackers commonly target three weaknesses:

1. **Weak authentication** (bad passwords) - authentication proves who you are.
  - It can be something you know (password, PIN), something you are (fingerprint), or something you have (phone/SMS)
  - Passwords are attacked the most as many people use easy or reused passwords (e.g., 123456, password, qwerty).
  - Easy passwords let attackers access private accounts and data.
  - ⚠️ Strong, unique passwords are essential.

2. **Weak file permissions** - systems should follow least privilege: only the right people can access files.
  - Weak permissions allow attackers to read files they shouldn’t (break confidentiality), change files they shouldn’t (break integrity)

3. **Malicious programs (malware)** - Malware can attack all three security pillars.
  - e.g. trojans can give attackers access to your system and files.
  - e.g. ransomware locks (encrypts) files and demands money to unlock them, attacking availability.

><details><summary>❓Which of the following is a strong password, in your opinion? iloveyou, 1q2w3e4r5t, LearnM00r, qwertyuiop  </summary>LearnM00r</details>
Solution: It uses uppercase, lowercase, numbers, it's not a common dictionary word, not a keyboard pattern and it's harder to guess or brute-force.

## Practical Example of OS Security ##

