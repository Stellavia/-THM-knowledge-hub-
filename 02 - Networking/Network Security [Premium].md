🔗 [Link to the Room](https://tryhackme.com/room/intronetworksecurity)

## 🏷️ **Topic:** Learn about network security, understand attack methodology, and practice hacking into a target server. ##

# 📚 Study Notes #


## Learning Objectives ##
- learn what is network security and its purpose
- what is CIA triad
- difference between HW and SW based security solution
- what is firewall, IDS, IPS, VPN concentrator
- and many more things ... 

### Introduction ###
- A computer network **is a group of connected computers and devices**.
- Network security focuses on protecting these devices, the connections between them, and the data they carry by ensuring confidentiality, integrity, and availability (CIA).

- Network security is achieved using **hardware and software solutions**:
  - **Hardware security solutions** (*these are physical devices used to protect networks*): **firewall appliance** (*controls incoming and outgoing traffic using predefined rules*), 
**IDS** (*Intrusion Detection System*, *detects attacks or intrusion attempts*), **IPS** (*Intrusion Prevention System*, *detects and actively blocks attacks*), **VPN concentrator** (*encrypts network traffic to protect data confidentiality and integrity*).

  - **Software security solutions** (*these are programs installed on systems*): **Antivirus software** (*detects and blocks malicious files*), **host firewall** (*software-based firewalls built into operating systems, e.g. Windows Defender Firewall, macOS firewall*). 

### Why network security matters ###

- Data breaches are extremely costly. According to IBM Security:

    - Average breach cost (2021): $4.24 million
    - Healthcare sector: ~$9.23 million
    - Education sector: ~$3.79 million

&nbsp;

>[!IMPORTANT]
>**Strong network security is essential to reduce financial loss and protect sensitive data.**

&nbsp;

---

><details><summary>❓What type of firewall is Windows Defender Firewall?</summary>Host Firewall</details>
>Solution: It runs on your computer and protects only that device, not the whole network.

--- 

&nbsp;

## Methodology ##

- Successful attacks require planning and information gathering, similar to planning wildlife photography, a military operation, or a burglary.

- Breaking into a network usually follows the **Cyber Kill Chain**, which **has seven steps**:

**1. Reconnaissance** – Gather information about the target (systems, users, IPs). <br>
**2. Weaponization** – Prepare malware or a malicious file. <br>
**3. Delivery** – Send the malicious file to the target (email, USB, etc.). <br>
**4. Exploitation** – Victim opens the file, triggering the attack. <br>
**5. Installation** – Malware installs on the system. <br>
**6. Command & Control (C2)** – Attacker gains remote control of the system. <br>
**7. Actions on Objectives** – Attacker achieves goals (e.g., data exfiltration). <br>
   

- The process is similar to a thief planning a break-in: observe first, plan entry, then steal valuables.

<img width="1140" height="508" alt="821ff7df89367ba6d12cbdacd669027a" src="https://github.com/user-attachments/assets/a96bc3c8-4412-410c-ae43-c3f1a773fd63" />


&nbsp;

---

><details><summary>❓During which step of the Cyber Kill Chain does the attacker gather information about the target</summary>Recon</details>
>Solution: The attacker gathers info about the target before launching the attack, which is first step

---
### Practical Example of Network Security

><details><summary>❓What is the password in the secret.txt file?</summary>ABC789xyz123</details>

---

><details><summary>❓What is the content of the flag.txt in the /root directory?</summary>THM{***_******_*****}</details>

---

><details><summary>❓What is the content of the flag.txt in the /home/librarian directory?</summary>THM{*********_*******_***********}</details>

---

