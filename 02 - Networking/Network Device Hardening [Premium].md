
🔗 [Link to the Room](https://tryhackme.com/room/networkdevicehardening)

## 🏷️Learn techniques for securing and protecting network devices from potential threats and attacks.

1. [Common Threat and Attack Vectors](#common-threat-and-attack-vectors)<br>
  1.1 [Difference between Network Devices and Endpoint Devices](#difference-between-network-devices-and-endpoint-devices)<br>
1.2 [Common Threats and Attack Vectors of Network Devices](#common-threats-and-attack-vectors-of-network-devices)<br>
2. [Common Hardening Techniques](#common-hardening-techniques)<br>
3. [Hardening Virtual Private Networks](#hardening-virtual-private-networks)<br>
4. [Hardening Routers, Switches and Firewalls](#hardening-routers-switches-and-firewalls)<br>
5. [Hardening Routers, Switches and Firewalls - More Techniques](#hardening-routers-switches-and-firewalls---more-techniques)<br>
6. [Important Tools for Network Monitoring](#important-tools-for-network-monitoring)<br>

&nbsp;

# 📚 Study Notes #

<!-- INTRODUCTION HERE -->
Network devices are the basic parts that make modern networks work. They help send, receive, control, and protect data as it moves between computers and networks.

There are different types of network devices. Some are very simple, like **hubs** and **repeaters**, which just **pass** **data** along. Others are more advanced, like **switches** and **routers**, which **direct traffic**. There are also devices that **balance traffic**, create **secure connections** (VPNs), and **protect networks** from attacks (intrusion prevention systems).

&nbsp;

# Common Threat and Attack Vectors

&nbsp;

## Difference between Network Devices and Endpoint Devices

Before learning more, it’s important to understand the difference:

- **Endpoint devices** are devices that send or receive data on a network.<br>
Examples: laptops, desktops, smartphones, tablets, printers, servers, and IoT devices.<br>
They are at the edge of the network and are used directly by people.

- **Network devices** manage and control the flow of data between endpoint devices.<br>
Examples: switches, routers, firewalls.<br>
They direct, filter, and protect network traffic.

&nbsp;

>[!NOTE]
> **Endpoints use the network.** <br>
> **Network devices run and manage the network.**

&nbsp;

<img width="1140" height="449" alt="image" src="https://github.com/user-attachments/assets/7fc38e2e-bcc6-4d9b-ae48-d08cb777bc20" />

## Common Threats and Attack Vectors of Network Devices

Modern ICT networks have grown rapidly and connected the world, however, this growth has also increased cyber attacks.

**Network devices are the backbone of these systems, so they must be secured.**

To protect **Confidentiality**, **Integrity**, and **Availability (CIA)**, we need to apply security hardening to network devices.

**Goals of security hardening:**
- Prevent unauthorized access and attacks
- Enforce access control policies
- Stop data theft
- Keep important systems available and running


|Threat|Description|Attack Vector|
|--------------------|----------------------------------|-----------------------------------------|
|Unauthorised access|Gain unauthorised control of a network device, and then the complete network.|Password attacks (brute force, dictionary & hybrid), Exploit known vulnerabilities, e.g. RCE, Social Engineering/Phishing attack to trick network administrators into disclosing sensitive information such as usernames and passwords of devices|
|Denial of Service (DoS)| Disruption of critical devices and services to make them unavailable to genuine users.| Flooding devices with fake requests, exploiting vulnerabilities in logical or resource handling, manipulating network packets|
|Man-in-the-Middle Attacks|Intercept the network requests between two parties by masquerading as each other to steal sensitive information or alter/manipulate the requests.|ARP spoofing, DNS spoofing, Rogue access points|
|Privilege escalation|Gaining higher-level privileges or rights to perform restricted actions, e.g. accessing sensitive information or executing malicious code.|Weak passwords or use of the same passwords for user and admin accounts, exploiting vulnerabilities, misconfigurations|
|Bandwidth theft/ hotlinking|Linking a bandwidth-intensive resource (image or video) from an external website to its original website, without permission. This can cause increased traffic to the original website.|Scraping large volumes of data, DoS attacks, malware attacks|

&nbsp;

---
><details><summary>❓The device that is used to control and manage network resource is called?</summary>Network device</details>
---
><details><summary>❓A threat vector that includes disruption of critical devices and services to make them unavailable to genuine users is called?</summary>Denial of Service</details>
---

&nbsp;

# Common Hardening Techniques

&nbsp;














&nbsp;

---
><details><summary>❓Suppose you are configuring a router; which of the following could be considered an insecure protocol: A: HTTPS, B: FTP, C: SSH, D: IPsec</summary>B</details>
---
><details><summary>❓The protocol for sending log messages to a centralised server for storage and analyse is called?</summary>Syslog</details>
---

&nbsp;

# Hardening Virtual Private Networks

&nbsp;














&nbsp;

---
><details><summary>❓Update the config file to use cipher AES-128-CBC. What is the flag value linked with the cipher directive?</summary>THM{C*****_U******_***1}</details>
---
><details><summary>❓Update the config file to use auth SHA512. What is the flag value linked with the auth directive?</summary>THM{A***_U******_**3}</details>
---
><details><summary>❓As per the config file, what is the port number for the OpenVPN server?</summary>1194</details>
---

&nbsp;

# Hardening Routers, Switches and Firewalls

&nbsp;














&nbsp;

---
><details><summary>❓Update the password of the router to TryHackMe123</summary>No answer needed</details>
---
><details><summary>❓WHat is the default SSH port configured for OpenWrt in the attached VM?</summary>22</details>
---
><details><summary>❓Go thourhg the General Settings option Under the System tab in the attached VM. The administrator has left a special message in the Notes section. What is the flag value?</summary>THM{S*******1}</details>
---
><details><summary>❓What is the default system log buffer size value for the OpenWrt router in the attached VM?</summary>64</details>
---
><details><summary>❓What is the start priority for the script uhttpd?</summary>50</details>
---

&nbsp;

# Hardening Routers, Switches and Firewalls - More Techniques

&nbsp;














&nbsp;

---
><details><summary>❓What is the name of the rule that accepts ICMP traffic from source zone WAN and destination zone as this device?</summary>Allow-Ping</details>
---
><details><summary>❓What is the name of the rule that forwards data coming from WAN port 9001 to LAN port 9002?</summary>THM_PORT</details>
---
><details><summary>❓What is the version number for the available apk package?</summary>2.12.2-1</details>
---

&nbsp;

# Important Tools for Network Monitoring

&nbsp;

















&nbsp;

---
><details><summary>❓Are network monitoring tools capable of detecting bandwidth bottlenecks? (yea/nay)</summary>yea</details>
---
&nbsp;

<!-- NO QUESTIONS -->



