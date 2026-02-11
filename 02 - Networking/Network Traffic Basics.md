🔗 [Link to the Room](https://tryhackme.com/room/networktrafficbasics)

## 🏷️ Learn what network analysis is, why it is essential, how to collect network traffic and which tools are available


# 📚 Study Notes 

&nbsp;

- **Network Traffic Analysis (NTA)** is the process of capturing, inspecting, and analyzing network data as it moves across a network. 
- Its goal is to **provide full visibility into what is happening inside and outside the network**. 
NTA is more than just using tools like Wireshark — it combines log correlation, deep packet inspection, and network flow analysis to achieve specific security goals.

&nbsp;

- NTA involves collecting traffic data, examining packets, reviewing logs, and analyzing network flows to understand communication patterns. 
- Analysts compare normal network behavior (baseline) with unusual activity to detect potential threats. 
- It is a key skill for both blue team (defensive) and red team (offensive) roles, especially for SOC analysts monitoring security events.

- Strong networking fundamentals make NTA much easier to understand.
- Recommended background knowledge: **Pre Security** and **Networking Essentials**.

&nbsp;

## What is the Purpose of Network Traffic Analysis

- **Network Traffic Analysis (NTA) helps** security teams **understand what is happening inside and outside a network**.
- Logs alone often don’t provide enough detail to determine whether activity is malicious.
- By inspecting actual network traffic content, analysts can uncover hidden threats such as command-and-control (C2) communication or data exfiltration.

- Basic logs (like DNS logs from a firewall) show metadata such as source IP, queried domain, query type, and timestamps.
- However, they usually do not show the actual content of the communication.

<img width="910" height="121" alt="image" src="https://github.com/user-attachments/assets/13c7bd7d-0605-4cac-a828-6a1fa2a51633" />


- For example, repeated DNS queries to the same domain with different subdomains may indicate **DNS tunneling** or **beaconing**.
- By capturing and inspecting packets, analysts can examine DNS responses and detect hidden data or encoded C2 commands (such as suspicious TXT records).
- This deeper inspection allows analysts to confirm whether the activity is malicious.

- The packet capture fragment below shows the content of a DNS reply that contains C2 commands:
<img width="555" height="318" alt="image" src="https://github.com/user-attachments/assets/732aebfb-4f66-4a3f-ace5-059d3e53de0a" />

- Logs provide limited visibility — mostly metadata, not full content.
- Repeated or unusual DNS queries may indicate tunneling or beaconing.
- Packet inspection reveals the actual content of communication.
- NTA helps detect threats like data exfiltration, malware downloads, and lateral movement.
- SOC analysts use NTA to validate alerts and reconstruct attacks.

>[!TIP]
>Always compare activity against a network baseline — abnormal spikes in DNS or HTTP traffic often signal compromise. <br>
>DNS TXT records are commonly abused for C2 communication. <br>
>If logs raise suspicion, move to packet-level analysis to confirm what’s really happening.
>

&nbsp;

---  
><details><summary>❓What is the name of the technique used to smuggle C2 commands via DNS?</summary>DNS tunneling</details>
---

## What Network Traffic can we observe?

---  
><details><summary>❓Look at the HTTP example in the task and answer the following question: What is the size of the ZIP attachment included in the HTTP response? Note down the answer in bytes.</summary>10485760</details>
---  
><details><summary>❓Which attack do attackers use to try to evade an IDS?</summary>fragmentation</details>
---  
><details><summary>❓What field in the TCP header can we use to detect session hijacking?</summary>sequence number</details>
---

## Network Traffic Sources and Flows

---  
><details><summary>❓Which category of devices generates the most traffic in a network?</summary>endpoint</details>
---  
><details><summary>❓Before an SMB session can be established, which service needs to be contacted first for authentication?</summary>kerberos</details>
---  
><details><summary>❓What does TLS stand for?</summary>Transport Layer Security</details>
---

## How can we observe Network Traffic?

---  
><details><summary>❓What is the lag found in the HTTP traffic in scenario 1? The flag has the format THM{}</summary>THM{***************}</details>
---  
><details><summary>❓What is the flag found in the DNS traffic in scenario 2? The flag has the format THM{}</summary>THM{**************}</details>
---
