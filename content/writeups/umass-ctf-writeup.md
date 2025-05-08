# UDMASS CTF Writeup

The **UMass Cybersecurity Club** organized **UMassCTF 2025**, a global cybersecurity competition featuring challenges in:

- Web exploitation  
- Cryptography  
- Reverse engineering  
...and more.

This is how I solved some of the challenges!

---

## 🔍 Challenge: Steganography + Cryptography

This challenge presented an **image filled with multiple QR codes**.

### Step 1: QR Analysis

I started by uploading the image to **Aperi'Solve**  
🔗 https://www.aperisolve.com

This revealed:
- A **hash**
- A **key**

![QR Image](qr.png)  
![QR Analysis on Aperi'Solve](qr-analyze.png)

---

### Step 2: Vigenère Cipher Decryption

The hash looked like it was encrypted using the **Vigenère cipher**.

Using **DCode's Vigenère Cipher Solver**  
🔗 https://www.dcode.fr/vigenere-cipher

I entered the hash and key and...  
💥 **Boom! The flag was revealed!**

![Vigenère Decryption](vigenere-decrypt.png)

---

## 🧪 Challenge: PCAP File Analysis

### Step 1: Making the File Usable

First, I changed file permissions:

```bash
chmod +x chall.pcapng
```

This allowed the file to be read/analyzed properly.

![File Prep](file.png)

---

### Step 2: Wireshark Inspection

I opened the file in **Wireshark** and applied the following filter:

```
frame contains "UMASS"
```

This pinpointed the **relevant packet**.

💥 **Boom! Another flag was revealed!**

![Wireshark](wireshark.png)

---

> _“Two halls uncovered, yet the path of learning stretches infinitely ahead—every solved challenge fuels the fire to conquer more.”_

---

### 🧰 Tools Used:

- **Aperi'Solve** (Image forensics)  
- **DCode.fr** (Cryptanalysis)  
- **Wireshark** (Network analysis)

---
