🔗 [Link to the Room](https://tryhackme.com/room/networkservices)

## 🏷️ Learn about, then enumerate and exploit a variety of network services and misconfigurations.

# 📚 Study Notes 

**== PAGE IN PROGRESS ==**

## Understanding SMB

- SMB is a network protocol that allows clients to access and share resources like files, printers, and other services over a network.
-  It works on a client-server model, where servers host resources and clients connect to use them. 
- SMB enables these actions remotely, making network resources feel like local ones.

- SMB operates as a request–response protocol: clients send requests and servers respond. 
- Connections typically use TCP/IP (NetBIOS over TCP/IP), NetBEUI, or IPX/SPX. 
- Once connected, clients can access shared folders, read and write files, and use printers or other shared services.

<img width="534" height="239" alt="image" src="https://github.com/user-attachments/assets/45c551e7-13ed-40a5-a396-68a933d7f34f" />

- Supported by Windows since Windows 95.
- Samba provides SMB support for Linux/Unix systems.
- Often targeted in network attacks due to misconfigurations or weak permissions.
  
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

- SMB enumeration is the process of collecting information from SMB services on a target machine to find useful data and possible attack paths. 
- It’s an important early step in security testing because it helps avoid using the wrong exploits and saves time. 
- Good enumeration often reveals users, shares, and system details.

**First, I recommend you to start the target machine and wait for it to fully boot.**

- Enumeration begins with a port scan to discover open services and system details. 
- If SMB is available, you can then check for shared folders and exposed data. 
- Tools like Enum4linux automate SMB enumeration and pull useful information from both Windows and Linux systems.

- **Enumeration** = information gathering before attempting exploitation.
- SMB shares can contain surprisingly sensitive files.
- Port scanning comes first (to find out as much info as you can about the services, apps, OS, ...), SMB probing comes after.
- **Enum4linux** is a go-to tool for quick SMB info gathering.

The syntax of Enum4Linux: `enum4linux [options] ip`

|TAG|FUNCTION|
|:---:|---------------------------------|
|-U|get userlist|
|-M|get machine list|
|-N|get namelist dump (different from -U and-M)|
|-S|get sharelist|
|-P|get password policy information|
|-G|get group and member list|
|-a|all of the above (full basic enumeration)|


>[!TIP]
>Enum4linux runs multiple Samba-based checks in one command, which makes it great for fast lab work.
>Using the -a option performs a full basic enumeration in one go — perfect for a first sweep.
>

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

- SMB exploitation can happen through real vulnerabilities, but more often it succeeds because of system misconfigurations. 
- A common example is anonymous SMB share access, where anyone can connect and read files. 
- This kind of access can expose sensitive data and help an attacker move toward getting a shell.

- After enumeration, you identify the SMB share location and any interesting shares worth accessing. 
- Instead of exploiting a software bug, you connect directly if permissions are too open. 
- The SMBClient tool (part of the Samba suite) is used to remotely connect and interact with SMB shares.

- **Connection syntax**: `smbclient //[IP]/[SHARE] -U [USERNAME] -p [PORT]`
- **Example**: `smbclient //10.10.10.10/secrets -U Anonymous -p 445`

- Once connected, you can browse and download files from the share.

- SMB attacks are often successful due to misconfiguration, not just CVEs.
- Anonymous share access is a common and dangerous mistake.
- Enumeration tells you which shares exist and which look valuable.
- SMBClient is the standard tool to connect to SMB shares.
- You can run help inside SMBClient to see available commands.

>[!TIP]
> Most useful SMBClient commands to remember:
> ls or dir → list files and folders
> cd [dir] → change directory
> get [file] → download a file to your attack machine
>

---  
><details><summary>❓What would be the correct syntax to access an SMB share called "secret" as user "suit" on a machine with the IP 10.10.10.2 on the default port?</summary>smbclient //10.10.10.2/secret -U suit -p 445</details>
---  
><details><summary>❓Great! Now you've got a hang of the syntax, let's have a go at trying to exploit this vulnerability. You have a list of users, the name of the share (smb) and a suspected vulnerability.</summary>No answer needed</details>
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
