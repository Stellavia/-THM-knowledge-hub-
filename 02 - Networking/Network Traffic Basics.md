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

<img width="1370" height="457" alt="image" src="https://github.com/user-attachments/assets/c2f3c1bd-7dbb-4845-b6f0-660e36735de8" />


### Application Layer

- At this layer, we see application headers and the actual payload (data).
- - The structure depends on the protocol (e.g., HTTP, DNS, FTP).

- For example, in an HTTP request we can see the requested file (e.g., suspicious_package.zip), the server response code (e.g., 200 OK), metadata like content type and file size.
  
<img width="583" height="515" alt="image" src="https://github.com/user-attachments/assets/56092a1c-3e5b-4925-800d-6b96054ed95c" />

- However, logs typically do not show the actual file content (the ZIP file itself). Only packet capture allows inspection of the full payload.

- Key Things We Can Observe
  - Requested resources (URLs, filenames)
  - Response codes (200, 404, etc.)
  - Headers (User-Agent, Content-Type, etc.)
  - Full payload (only via packet capture)

>[!NOTE]
> **Logs show what was requested — packet captures show what was actually delivered.**
>This is critical when checking for malware downloads or data exfiltration.
>

### Transport Layer

- Here, data is segmented and encapsulated using TCP or UDP headers.
- Logs often show source and destination port, TCP flags (SYN, ACK, PSH), basic connection info,
- But full packet captures reveal additional details like sequence numbers, acknowledgment numbers, window sizes
- These fields are important for detecting attacks like session hijacking; for example a sudden jump in TCP sequence numbers may indicate a malicious packet injection attempt.

- Key Things We Can Observe
  - TCP 3-way handshake behavior
  - Port usage patterns
  - Suspicious flag combinations
  - Sequence number anomalies

>[!CAUTION]
> **A large, unexpected jump in TCP sequence numbers can signal session injection or hijacking attempts.**
>

### Internet Layer

- This layer adds the IP header.
- Logs usually include source IP, destination IP, TTL (Time To Live)
- However, full packet inspection reveals fragment offset, total length, fragmentation flags
- These are essential when detecting fragmentation attacks, such as overlapping fragments used to bypass IDS systems.

- Key Things We Can Observe
  - IP communication paths
  - Fragmentation behavior
  - TTL anomalies
  - Suspicious packet splitting

- Overlapping IP fragments can be used to evade detection systems, only full packet inspection reveals these manipulation attempts.

## Link Layer

- At this layer, packets receive MAC addressing information.
- Logs usually show source MAC and destination MAC
- But full captures help detect ARP poisoning, MAC spoofing, duplicate MAC usage across interfaces, excessive gratuitous ARP traffic

- For example in an ARP poisoning attack, one device may repeatedly claim to own multiple IP addresses using the same MAC address.

<img width="1298" height="195" alt="image" src="https://github.com/user-attachments/assets/965d7f69-1632-47ca-88af-409883efacf1" />

- Key Things We Can Observe
  - MAC address mappings
  - ARP request and reply behavior
  - Spoofed MAC addresses

>[!CAUTION]
> If one MAC address keeps claiming multiple IPs, you may be seeing ARP poisoning in action.

Each TCP/IP layer gives us different visibility into network behavior. Logs only provide partial insight, while packet captures reveal the complete picture.

- Understanding what can be observed at every layer allows analysts to detect hidden attacks, investigate suspicious behavior, identify evasion techniques, validate security alerts

- Network traffic analysis isn’t just about watching traffic — it’s about understanding how every layer contributes to the full story.

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
