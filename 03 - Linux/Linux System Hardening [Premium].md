🔗 [Link to the Room](https://tryhackme.com/room/linuxsystemhardening)

## 🏷️ **Topic:** Learn how to improve the security posture of your Linux systems. ##

# 📚 Study Notes #

- Linux is a secure and cost-effective alternative to systems like Windows Server.
- Hosting on Linux can save money on licensing and hardware.
- While not always the best choice, it works well in many cases.
- Before using it, it’s important to secure the system, a process called **Linux hardening**.


## Learning Objectives ##

- in this room you will learn how to secure Linux by focusing on:
  - Physical security
  - Encrypting filesystems
  - Setting up firewalls
  - Managing remote access
  - Controlling software and services
  - Keeping the system updated
  - Monitoring logs

<img width="595" height="382" alt="image" src="https://github.com/user-attachments/assets/ab5dd837-9e0f-4cd6-aa4b-82f83ad79670" />

## Physical Security ##

- Physical security is the first layer of defense.
- If an attacker can access your computer physically, they can steal disks or reset passwords, even on Linux.
- This is why the saying goes: **“boot access = root access.”**

- To protect your system:
  - Keep computers in secure locations.
  - Use complex system passwords.
  - For personal systems, consider adding a BIOS/UEFI boot password.
  - You can also add a GRUB password to prevent unauthorized boot changes or root access (`grub2-mkpasswd-pbkdf2 `generates the hash).

⚠️ GRUB passwords aren’t useful for cloud servers, since you can’t access the physical machine.

Physical security is crucial because attackers with physical access can cause serious damage. 
GRUB passwords and boot passwords add extra layers, but you should also have a plan if disks are stolen.  

📝 GRUB [The GRand Unified Bootloader] is a program that starts your Linux system when you turn on your computer. It lets you choose which operating system to boot and can be used to access advanced boot options.


Answers for these two questions are in the text (or you can search it up online):
><details><summary>❓ What command can you use to create a password for the GRUB bootloader?</summary>grub2-mkpasswd-pbkdf2</details>
Solution: It's a tool that creates a secure password hash for GRUB, so only authorized users can change boot settings or access root.

><details><summary>❓What does PBKDF2 stand for? </summary>Password-Based Key Derivation Function 2</details>
