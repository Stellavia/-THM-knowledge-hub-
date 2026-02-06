🔗 [Link to the Room](https://tryhackme.com/room/hardeningbasicspart2)

## 🏷️ **Topic:** Continue learning about hardening

# 📚 Study Notes #

>[!NOTE]
>All tasks for this room were completed using Ubuntu 18.04 LTS. That being said, pretty much everything that applies to 18.04 can apply to 20.04 as well. If you take what you learn out of this room and try to apply it in the real world for practice and fun and something does not work, be sure to check the documentation for what you are trying to do.
>

## Chapter 3 Quiz

---
><details><summary>❓Which SSH Protocol version is the most secure?</summary>2</details>
---
><details><summary>❓This is a random, arbitrary number, used as the session key, that is used to encrzpt GPG.</summary>nonce</details>
---
><details><summary>❓Yey/Ney - GPG is based on the OpenPGP standard</summary>Yey</details>
---
><details><summary>❓What is the command to symmetrically encrypt a file with GPG?</summary>gpg -c</details>
---
><details><summary>❓What is the command to asymmetrically encrypt a file with GPG?</summary>gpg -e</details>
---
><details><summary>❓What is the command to create SSH keys?</summary>ssh-keygen</details>
---
><details><summary>❓Where are ssh keys stored in a user's home directory?</summary>.ssh</details>
---
><details><summary>❓What option needs to be set to select the type of key to generate for SSH?</summary>-t</details>
---
><details><summary>❓The SSH configuration options presented in this chapter were found in what file (full path)?</summary>/etc/ssh/sshd_config</details>
---

## GNU Privacy Guard

<img width="636" height="261" alt="image" src="https://github.com/user-attachments/assets/6282cc87-bf17-42aa-83c6-1580a3e43c91" />

- To understand GPG, you first need to understand PGP, the system it’s based on.

### Pretty Good Privacy (PGP) 

- PGP is a system used to encrypt and decrypt emails and files.
- It uses both types of encryption: **Asymmetric encryption** (public & private keys) and **Symmetric encryption** (a shared secret key)

### How PGP encryption works (step by step)

1. You write an email
2. A random one-time session key is created (This is also called a nonce)
3. The email is encrypted using this session key
4. The session key itself is encrypted using the recipient’s public key
5. Both the encrypted email and encrypted session key are sent

To decrypt:
1. The recipient uses their private key to unlock the session key
2. The session key is then used to decrypt the message back to readable text

### GNU Privacy Guard (GPG)
- GPG is an open-source implementation of the OpenPGP standard (which PGP follows).
- In simple terms: GPG = the modern, free version of PGP
- It’s widely trusted and heavily tested

- GPG offers:
  - Easy encryption for emails and files
  - Extremely strong security (PGP is considered practically unbreakable)
  - Asymmetric encryption, so you don’t need to share passwords
  - Better overall security compared to password-based encryption
    
- GPG also comes pre-installed on Ubuntu, which makes it very convenient.

### Creating GPG keys

- Before using GPG, you must create a key pair: **Public key** (shared with others) and **Private key** (kept secret)
- You generate keys with `gpg --gen-key`
- What happens next:
  - GPG asks for basic info (name, email, etc.)
  - It generates random data for the keys
  - You may be asked to move your mouse or type to add randomness
- Once finished:
  - GPG creates configuration files in your home directory
  - A `.gnupg` directory is created

- To check that your keys were created successfully use `gpg --list-keys`

## Encrypting Your Files

- GPG lets you encrypt files in two different ways:
  1. Symmetric encryption (one shared secret)
. Asymmetric encryption (public + private keys)


### 1. Symmetric Encryption (password-based)

- Symmetric encryption uses one secret (a passphrase) to both encrypt the file and decrypt the file
- Anyone who knows the passphrase can read the file.

- How it works:
  - You encrypt a file with `gpg -c yourfile.txt`
  - What happens: GPG asks you to enter a passphrase; the file is encrypted into a `.gpg` file, you’ll need the same passphrase to decrypt it

>[!IMPORTANT]
> This passphrase is not your GPG key passphrase
> GPG may leave the original file unencrypted
> You should delete it using rm or shred if it’s sensitive
>

### Decrypting

- To read the file use `gpg -d yourfile.txt.gpg`
- You’ll be prompted for the passphrase, then the contents are displayed.

### 2. Asymmetric Encryption (key-based)

- Asymmetric encryption uses two keys public key (encrypt) and private key (decrypt)

>[!IMPORTANT]
> Public keys can be shared
> Private keys must NEVER be shared
>

### 3. Sharing public keys

- To export a public key use `gpg --export -a -o publickey.asc`
- This creates a text-based (ASCII armored) public key file.
- To import someone else’s public key use `gpg --import publickey.asc`
- Once imported, you can encrypt files for that person.

### 4. Encrypting a file for someone else

Example
- Nick encrypts a file like this: `gpg -e document.txt`
- GPG will ask who the recipient is (based on imported public keys).
- The encrypted file can be sent over email, chat, file sharing, even insecure channels

### 5. Decrypting the file
- When Spooky decrypts: `gpg -d document.txt.gpg`
- He is prompted for his private key passphrase.
- After that, the file is decrypted and readable.

>[!NOTE]
> Symmetric encryption is simple and fast, but requires sharing a secret
> Asymmetric encryption is more secure and scalable
> GPG allows safe file sharing without exchanging passwords
> Private keys are extremely sensitive — protect them at all costs
>

## SSH Protocol 1

- In your `/etc/ssh/sshd_config` file, if you see `Protocol 1` or `Protocol 1, 2`
- you need to disable Protocol version 1 asap.
- It's available to run on Legacy machines but has been compromised and is no longer considered secure. SSH Protocol Version 2 is the current, more secure version of SSH.

## Creating an SSH Key Set

- Logging in with a password is less secure, hence SSH keys are the safest way to log in
- Keys consist of a public key (shared) and a private key (kept secret)

### Generating SSH keys

- as a user run `ssh-keygen`
- Defaults to creating keys in `~/.ssh/`
- Generates both public (`id_rsa.pub`) and private (`id_rsa`) keys
<img width="514" height="374" alt="image" src="https://github.com/user-attachments/assets/1e749992-67f4-4c3e-bc9c-a234861c7c9b" />

>[!IMPORTANT]
>Public key = shared with the server
>Private key = never share

### Copying your public key to a remote server

- Use `ssh-copy-id` (example: `ssh-copy-id username@remote-host`)
  - this automatically copies your public key to the server
- or do manual copy = on the remote server run:
  `mkdir -p ~/.ssh`
  `cat /home/user/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`
  `chmod -R go= ~/.ssh`
- this adds your public key to `authorized_keys` and fixes permissions to secure the `.ssh` directory

- By default, ssh-keygen uses RSA 2048 bits.
- You can create stronger keys following NIST recommendations:
  - RSA 3072 bits: `ssh-keygen -t rsa -b 3072`
  - ECDSA 384 bits (smaller, faster, just as strong): `ssh-keygen -t ecdsa -b 384`
- Max ECDSA is 521 bits, but 384 is recommended for security and efficiency.


>[!IMPORTANT]
> SSH keys = safer than passwords
> Always protect your private key
> Share only your public key
> Use modern algorithms (RSA ≥3072 or ECDSA ≥384) for stronger security
> Correct permissions on .ssh and authorized_keys are critical
>


## Disable Username & Password SSH Login





## X11 Forwarding & SSH Tunneling

<!-- No Questions -->

## Improving SSH Logging

<!-- No Questions -->

## Chapter 4: Mandatory Access Control

<!-- No Questions -->

## Introduction to AppArmor

<!-- No Questions -->

## AppArmor Command Line Utilities

<!-- No Questions -->

## Chapter 4 Quiz

---
><details><summary>❓Where are the AppArmor profiles located?</summary>/etc/apparmor.d</details>
---
><details><summary>❓This directory includes partial profiles to be used in your own custom profiles</summary>abstractions</details>
---
><details><summary>❓This punctuation mark is REQUIRED at the end of every rule in a profile</summary>.</details>
---
><details><summary>❓This AppArmor mode enforces the profiles but also logs them</summary>audit</details>
---
><details><summary>❓This command checks the status of AppArmor</summary>aa-status</details>
---

## Chapter 3: SSH and Encryption

<!-- No Questions -->

## Conclusion & Optional Challenges

<!-- No Questions -->
