🔗 [Link to the Room](https://tryhackme.com/room/introtonetworking)

## 🏷️ An introduction to networking theory and basic networking tools

# 📚 Study Notes 

**== PAGE IN PROGRESS ==**

## The OSI Model: An Overview

---  
><details><summary>❓Which layer would choose to send data over TCP or UDP?</summary>4</details>
---  
><details><summary>❓Which layer checks received information to make sure that it hasn't been corrupted?</summary>2</details>
---  
><details><summary>❓In which layer would data be formatted in preparation for transmission?</summary>2</details>
---  
><details><summary>❓Which layer transmits and receives data?</summary>1</details>
---  
><details><summary>❓Which layer encrypts, compress, or otherwise transforms the initial data to give it a standardised format?</summary>6</details>
---  
><details><summary>❓Which layer tracks communications between the host and receiving computers?</summary>5</details>
---  
><details><summary>❓Which layer accepts communication request from applications?</summary>7</details>
---  
><details><summary>❓Which layer handles logical addressing?</summary>3</details>
---  
><details><summary>❓When sending data over TCP, what would you call the "bite-sized" pieces of data?</summary>Segments</details>
---  
><details><summary>❓[Research] Which layer would the FTP protocol communicate with?</summary>7</details>
---  
><details><summary>❓Which transport layer protocol would be best suited to transmit a live video?</summary>UDP</details>
---

## Encapsulation

---  
><details><summary>❓</summary>How would you refer to data at layer 2 of the encapsulation process (with the OSI model)?</summary>Frames</details>
---  
><details><summary>❓How would you refer to data at layer 4 of the encapsulation process (with the OSI model), if the UDP protocol has been selected?</summary>Datagrams</details>
---  
><details><summary>❓What process would a computer perform on a received message?</summary>De-encapsulation</details>
---  
><details><summary>❓Which is the only layer of the OSI model to add a trailer during encapsulation?</summary>Data Link</details>
---  
><details><summary>❓Does encapsulation provide an extra layer of security (Aye/Nay)?</summary>Aye</details>
---

## The TCP/IP Model

---  
><details><summary>❓Which model was introduced first, OSI or TCP/IP?</summary>TCP/IP</details>
---  
><details><summary>❓Which layer of the TCP/IP model covers the functionality of the Transport layer of the OSI model (Full Name)?</summary>Transport</details>
---  
><details><summary>❓Which layer of the TCP/IP model covers the functionality of the Session layer of the OSI model (Full Name)?</summary>Application</details>
---  
><details><summary>❓The Network Interface layer of the TCP/IP model covers the functionality of two layers in the OSI model. These layers are Data Link, and? ...(Full Name)?</summary>Physical</details>
---  
><details><summary>❓Which layer of TCP/IP model handles the functionality of OSI network layer?</summary>Internet</details>
---  
><details><summary>❓What kind of protocol is TCP?</summary>Connection-based</details>
---  
><details><summary>❓What is SYN short for?</summary>Synchronise</details>
---  
><details><summary>❓What is the second step of the three way handshake?</summary>SYN/ACK</details>
---  
><details><summary>❓What is the short name for "Acknowledgement" segment in the three-way handshake?</summary>ACK</details>
---

## Networking Tools: Ping

---  
><details><summary>❓What command would you use to ping the bbc.co.uk website?</summary>ping bbc.co.uk</details>
---  
><details><summary>❓Ping muirlandoracle.co.uk What is the IPv4 address?</summary>217.160.0.152</details>
---  
><details><summary>❓What switch lets you change the interval of sent ping requests?</summary>-i</details>
---  
><details><summary>❓What switch would allow you to restrict requests to IPv4?</summary>-4</details>
---  
><details><summary>❓What switch would give you a more verbose output?</summary>-v</details>
---

## Networking Tools: Traceroute

---  
><details><summary>❓What switch would you use to specify an interface when using Traceroute?</summary>-i</details>
---  
><details><summary>❓What switch would you use if you wanted to use TCP SYN requests when tracing the route?</summary>-T</details>
---  
><details><summary>❓[Lateral Thinking] Which layer of the TCP/IP model will traceroute run on by default (Windows)?</summary>Internet</details>
---

## Networking Tools: WHOIS

---  
><details><summary>❓What is the registrant postal code for facebook.com</summary>94025</details>
---  
><details><summary>❓When was the facebook.com domain first registered (Format: DD/MM/YYYY)</summary>29/03/1997</details>
---  
><details><summary>❓Which city is the registrant based in?</summary>Redmont</details>
---  
><details><summary>❓[OSINT] What is the name of the golf course that is near the registrant address for microsoft.com?</summary>Bellevue Golf Course</details>
---  
><details><summary>❓What is the registered Tech Email for microsoft.com?</summary>msnhst@microsoft.com</details>
---

## Networking Tools: Dig

---  
><details><summary>❓What is DNS short for?</summary>Domain Name System</details>
---  
><details><summary>❓What is the first type of DNS server your computer would query when you search for a domain?</summary>Recursive</details>
---  
><details><summary>❓What type of DNS server contains records specific to domain extensions (i.e. .com, .co.uk*, etc)*? Use the long version of the name.</summary>Top-Level Domain</details>
---  
><details><summary>❓Where is the very first place your computer would look to find the IP address of a domain?</summary>Hosts File</details>
---  
><details><summary>❓[Research] Google runs two public DNS servers. One of them can be queried with the IP 8.8.8.8, what is the IP address of the other one?</summary>8.8.4.4</details>
---  
><details><summary>❓If a DNS query has a TTL of 24 hours, what number would the dig query show?</summary>86400</details>
---
