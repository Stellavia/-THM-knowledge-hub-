🔗 [Link to the Room](https://tryhackme.com/room/networkservices)

## 🏷️ Learn about, then enumerate and exploit a variety of network services and misconfigurations.

# 📚 Study Notes 

**== PAGE IN PROGRESS ==**

## Understanding SMB

---  
><details><summary>❓What does SMB stand for?</summary>Server Message Block</details>
---  
><details><summary>❓What type of protocol is SMB?</summary>response-request</details>
---  
><details><summary>❓What protocol suite do clients use to connect to the server?</summary>TCP/IP</details>
---  
><details><summary>❓What systems does Samba run on?</summary>Unix</details>
---

## Enumerating SMB

---  
><details><summary>❓Conduct an nmap scan of your choosing, How many ports are open?</summary>3</details>
---  
><details><summary>❓What ports is SMB running on? Provide the ports in ascending order.</summary>139/445</details>
---  
><details><summary>❓Let's get started with Enum4Linux, conduct a full basic enumeration. For starters, what is the workgroup name?</summary>WORKGROUP</details>
---  
><details><summary>❓What comes up as the name of the machine?</summary>POLOSMB</details>
---  
><details><summary>❓What operating system version is running?</summary>6.1</details>
---  
><details><summary>❓What share sticks out as something we might want to investigate?</summary>profiles</details>
---

## Exploiting SMB

---  
><details><summary>❓What would be the correct syntax to access an SMB share called "secret" as user "suit" on a machine with the IP 10.10.10.2 on the default port?</summary>smbclient //10.10.10.2/secret -U suit -p 445</details>
---  
><details><summary>❓Does the share allow anonymous access? Y/N?</summary>Y</details>
---  
><details><summary>❓Great! Have a look around for any interesting documents that could contain valuable information. Who can we assume this profile folder belongs to?</summary>John Cactus</details>
---  
><details><summary>❓What service has been configured to allow him to work from home?</summary>ssh</details>
---  
><details><summary>❓Okay! Now we know this, what directory on the share should we look in?</summary>.ssh</details>
---  
><details><summary>❓This directory contains authentication keys that allow a user to authenticate themselves on, and then access, a server. Which of these keys is most useful to us?</summary>id_rsa</details>
---  
><details><summary>❓What is the smb.txt flag?</summary>THM{***_**_***_**?}</details>
---

## Understanding Telnet

---  
><details><summary>❓Is Telnet a client-server protocol (Y/N)?</summary>Y</details>
---  
><details><summary>❓What has slowly replaced Telnet?</summary>SSH</details>
---  
><details><summary>❓How wouold you connect to a Telnet server with the IP 10.10.10.3 on port 23?</summary>telnet 10.10.10.3 23</details>
---  
><details><summary>❓The lack of what, means that all Telnet communication is in plaintext?</summary>encryption</details>
---

## Enumerating Telnet

---  
><details><summary>❓How many ports are open on the target machine? Note: you may need to scan non-standard ports too.</summary>1</details>
---  
><details><summary>❓What port is this?</summary>8012</details>
---  
><details><summary>❓This port is unassigned, but still lists the protocol it's using, what protocol is this?</summary>tcp</details>
---  
><details><summary>❓Now re-run the nmap scan, without the -p- tag, how many ports show up as open?</summary>0</details>
---  
><details><summary>❓Based on the title returned to us, what do we think this port could be used for?</summary>a backdoor</details>
---  
><details><summary>❓Who could it belong to? Gathering possible usernames is an important step in enumeration.</summary>Skidy</details>
---

## Exploiting Telnet

---  
><details><summary>❓Great! It's and open telnet connection! What welcome message do we receive?</summary>SKIDY'S BACKDOOR.</details>
---  
><details><summary>❓Let's try to executing some commands, do we get a return on any input we enter into the telnet session? (Y/N)</summary>N</details>
---  
><details><summary>❓Now, use the command "ping [local THM IP\ -c 1" through the telnet session to see if we're able to execute system commands. Do we receive any pings? Note, you need to preface this with .RUN (Y/N)</summary>Y</details>
---  
><details><summary>❓What word does the generated payload start with?</summary>mkfifo</details>
---  
><details><summary>❓What would the command look like for the listening port we selected in our payload?</summary>nc -lvnp 4444</details>
---  
><details><summary>❓Success! What is the contents of flag.txt?</summary>THM{***_***_***_******_****}</details>
---

## Understanding FTP

---  
><details><summary>❓What communications model does FTP use?</summary>client-server</details>
---  
><details><summary>❓What's the standard FTP port?</summary>21</details>
---  
><details><summary>❓How many modes of FTP connection are there?</summary>2</details>
---
## Enumerating FTP

---  
><details><summary>❓How many ports are open on the target machine?</summary>3</details>
---  
><details><summary>❓What port is ftp running on?</summary>21</details>
---  
><details><summary>❓What variant of FTP is running on it?</summary>vsftpd</details>
---  
><details><summary>❓What is the name of the file in the anonymous FTP directory?</summary>PUBLIC_NOTICE.txt</details>
---  
><details><summary>❓What do we think a possible username could be?</summary>mike</details>
---

## Exploiting FTP

---  
><details><summary>❓What is the password for the user "mike"?</summary>password</details>
---  
><details><summary>❓What is ftp.txt?</summary>THM{***_***_***_***_****}</details>
---  
