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

## Filesystem Partitioning and Encryption ##

- Disk encryption protects data if a device is stolen or physically accessed.
- Encrypted data is unreadable without the correct password, making the disk useless to attackers.

- Most Linux systems use LUKS (Linux Unified Key Setup) for disk encryption.
- LUKS encrypts a partition using a master key, which is protected by one or more user passwords = this allows multiple users to unlock the same encrypted disk with different passwords.
- LUKS supports strong encryption algorithms and securely derives keys from passwords using PBKDF2 = The actual data on the disk is encrypted with the master key.

📝 In a simple wording **LUKS** [Linux Unified Key Setup] is a tool that encrypts Linux disks so data can’t be read without a password.

📝 **PBKDF2** is a method that turns a password into a strong encryption key.

📝 **Cryptsetup** is a command-line tool to set up and manage encrypted Linux partitions.
  

- Linux distributions usually provide a graphical way to encrypt disks, but encryption can also be set up from the command line using cryptsetup. Once encrypted, the partition must be unlocked, formatted, and mounted before use.

- Encryption is an essential layer of security, especially to protect data if disks or devices are stolen.

><details><summary>❓What does LUKS stand for?</summary>Linux Unified Key Setup</details>

><details><summary>❓We cannot attach external storage to the VM, so we have created a /home/tryhackme/secretvault.img file instead. It is encrypted with the password 2N9EdZYNkszEE3Ad. To access it, you need to open it using cryptsetup and then mount it to an empty directory, such as myvault. What is the flag in the secret vault?</summary>THM{LUKS_not_LUX}</details>

Solution: Check the Question Hint provided by THM: `sudo cryptsetup open --type luks secretvault.img myvault && sudo mount /dev/mapper/myvault myvault/`. Then you can read your flag with command `cat task3_flag.txt`
