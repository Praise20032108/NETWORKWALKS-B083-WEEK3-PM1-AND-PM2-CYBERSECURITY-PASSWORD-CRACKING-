# 🔓 Week 3 — Password Cracking: Encrypted PDFs

Part of my cybersecurity learning journey at **NetworkWalks**, under the guidance of instructor **Waqas Karim (CCIE)**.

## 📌 Overview

This week's challenge focused on **password cracking** — recovering the password of an encrypted PDF to prove how quickly a weak password can be broken. The same locked PDF was cracked using **two different methods**, both relying on the same core technique: extract the password hash from the file, then run a wordlist attack against it until it cracks.

## 🛠️ Tools Used

- **John the Ripper (Jumbo)** — CLI password cracking tool
- **Johnny** — GUI front-end for John the Ripper
- **pdf2john** — utility to extract a crackable hash from a password-protected PDF
- **NetworkWalks Hash Calculator** — browser-based tool to extract PDF hashes and crack passwords, no install required

## 🧩 Method 1: John the Ripper + Johnny (GUI)

1. Opened **Johnny**, pointed it to the local `john.exe` executable (John the Ripper Jumbo 1.9.0).
2. Loaded the password hash extracted from the locked PDF.
3. Ran the attack against a wordlist.
4. Result: **password cracked — `password1`**, format `PDF` (`$pdf$4*4*128...`).

| Step | Screenshot |
|---|---|
| Johnny configured with John the Ripper executable | `JTR1.jpeg` |
| Attack in progress (41% complete, hashes cracking) | `JTR2.jpeg` |
| Password successfully recovered (`password1`) | `JTR3.jpeg` |

## 🌐 Method 2: NetworkWalks Hash Calculator (Browser-Based)

1. Visited [networkwalks.com/hash-calculator](https://networkwalks.com/hash-calculator/).
2. Uploaded the same locked PDF (`My Locked PDF2.pdf`) — parsed entirely client-side, nothing stored on the server.
3. Tool extracted a **pdf2john / hashcat-compatible hash** directly in the browser.
4. Same hash, same wordlist logic — cracked with zero installation.

| Step | Screenshot |
|---|---|
| PDF uploaded to Hash Calculator | `JTR4.jpeg` |
| Hash extracted and displayed | `HASH_CALCULATOR.jpeg`, `HASH_CALCULATOR2.jpeg` |

## 🚩 Flag Captured

```
nw{networkwalks_persistence_jtr_270521}
```

## 💡 Key Takeaway

Encryption is only as strong as the password protecting it. A "locked" PDF secured with a short or common password (like `password1`) can be cracked in seconds with a basic wordlist attack. **Long, random, and unique passwords** are what actually stand between your files and an attacker.

## 🙏 Acknowledgements

Thanks to instructor **Waqas Karim (CCIE)** for the guidance throughout this challenge.

---

**Week 4 — let's go 🚀**
