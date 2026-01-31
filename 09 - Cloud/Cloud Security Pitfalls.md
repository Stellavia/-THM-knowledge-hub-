🔗 [Link to the Room](https://tryhackme.com/room/cloudsecuritypitfalls)

## 🏷️ **Topic:** Explore the risks companies face when migrating to the cloud, and learn how to address them in a SOC. ##

# 📚 Study Notes #

- Many companies move their systems from on-premises to the cloud to save money and improve stability and security. However, the cloud also brings new security risks. If these risks are not understood, cloud systems can be less secure than before.
- This beginner room explains common cloud security risks and mistakes. It also shows how a SOC analyst can help protect cloud environments.

## Learning Objectives ##

- Learn the cloud models: IaaS, PaaS, SaaS
- Understand basic cloud security risks
- Learn the basics of cloud security
- Understand why monitoring cloud systems is challenging for SOC teams

## What Is Cloud ##

- The cloud means using computers and services over the internet instead of owning your own servers.
- You don’t buy hardware; You don’t maintain it; You just use it and pay for what you need;
- Examples: AWS, Google Drive

☁️ IaaS – You manage the OS

- Infrastructure as a Service
- You get a virtual computer 
- You install and manage the operating system and software
- The cloud provider manages the hardware
- Example: AWS, Azure, Google Cloud
- Basically it's like renting an empty apartment: you bring the furniture.

☁️ PaaS – You write code

- Platform as a Service
- You write code, Click deploy, the provider handles servers, OS, and setup
- Examples: Vercel, Heroku, Google App Engine, TryHackMe rooms
- It's like renting a furnished apartment: just move in.

☁️ SaaS – You just use it

- Software as a Service
- Ready-to-use software; No installation; Works in a browser;
- Examples: Google Docs. Gmail, Dropbox, Slack
- Basically like staying in a hotel: everything is done for you.

✅ IaaS → you manage most things 

✅ PaaS → you manage code only 

✅ SaaS → you manage nothing 

><details><summary>❓Which cloud model allows you to migrate a big on-premises network to the cloud?</summary>IaaS</details>
Solution: This is mentioned in the text as well as you can easily google it :)

><details><summary>❓Which cloud model do Elastic Cloud and CrowdStrike Falcon fit into?
Note: You may need to perform external research to answer this question. </details>SaaS</summary>
Solution: Same as previous one - search for it on the web.

## Security of the Cloud ##

- The cloud uses the same tech as on-prem systems (Linux, TCP/IP, etc.)
- The cloud is not magic — it’s basically someone else’s computer
- Cloud systems can be attacked, just like local computers
- Security of the provider’s infrastructure is called “Security of the cloud”


### Risk: Cloud Provider Vulnerabilities ###

- Big providers (AWS, Google Cloud) are well secured, but not perfect - If breached, attackers often target large customers = This is a supply chain risk.

- Always apply basic defenses:
  - Network segmentation
  - Login monitoring
  - Endpoint monitoring
  - Smaller or less-known providers are higher risk

- Past incidents show:
  - Malware deployed to all VMs (IaaS breaches)
  - Sensitive data leaked (SaaS breaches)

- Choose cloud providers carefully and be careful what data you trust them with.


### Risk: Poor Visibility in the Cloud ###

- Users cannot see inside the cloud provider’s internal systems
- Some attacks happen entirely inside SaaS infrastructure
- SOC teams cannot access provider internal logs, this makes detection very difficult

- SaaS risks:
  - Token theft
  - Data exfiltration
  - Shadow IT (employees using unapproved SaaS tools) = this can lead to unexpected data breaches.

### Example Cloud Incidents ###

1. Okta (SaaS, 2023): Support system breached; session tokens exposed; attackers logged into customer tenants.
2. BeyondTrust (SaaS, 2024): Remote Support SaaS compromised; attackers gained remote access to customers.
3. Google Cloud (IaaS, 2025): Cloud Run vulnerability; unauthorized access to container images.

⚠️***Cloud ≠ fully safe***
You trade control and visibility for convenience.

><details><summary>❓Is the cloud provider responsible for securing and monitoring its own infrastructure (Yea/Nay)? </details> Yea</summary>
Solution: Cloud providers are responsible for securing and monitoring their own infrastructure (physical data centers, HW, networking, Virtualization layer) = this is called "Security of the cloud". You as a customer are responsible for what you put in.

><details><summary>❓But should you trust the cloud provider without watching for supply chain threats? (Yea/Nay) </details> Nay </summary>
Solution: Cloud providers can be breached and that would affect many customers at once.

## Security in the Cloud ##

- You are responsible for securing your cloud resources: VMs (IaaS), Apps (PaaS), SaaS accounts & credentials.
- Treat cloud resources like on-prem systems → monitor & harden them.

### Cloud Migration Pitfalls ###

- Moving old VMs or files to the cloud doesn’t make them secure as cloud has new, cloud-specific threats.
- On-premises security practices often don’t work in the cloud.
- Example: Weak passwords without MFA are dangerous in public clouds.

### Logging in the Cloud ###

- You can’t install your usual SIEM tools in the cloud like you do on-premises. Instead, you have to use the cloud provider’s logging tools (e.g., AWS CloudTrail)

- Problems you might face with cloud logs:
  - Extra cost – some logs require paid plans
  - Messy or incomplete logs – not all info is there or easy to read
  - Hard to connect to your SIEM, especially for SaaS apps

### Cloud Incidents ###

- Capital One (AWS misconfig) → 1M Social Insurance Numbers stolen
- Various SaaS breaches → caused by weak passwords, leaked API keys, stolen cookies → attackers steal data


><details><summary>❓Does moving an unpatched server to the cloud make it secure again? (Yea/Nay) </details> Nay </summary>
Solution: Moving an old, unpatched server to the cloud doesn't fix its vulnerabilities as the server has the same security flaws as it had.
⚠️ **Cloud ≠ automatic security — it helps with availability and hardware, but doesn't fix your mistakes.**

><details><summary>❓ What is the first major obstacle to integrating most cloud products with a SIEM?  </details> Paid Logs </summary>
Solution: Many cloud providers charge extra to export logs or use advanced logging features and if your SIEM relies on these logs, you can’t collect everything for free.


## Summary ##

><details><summary>❓ </details> </summary>
><details><summary>❓ </details> </summary>
