# 🕵️‍♂️ TryHackMe - Security Footage

> **Category:** Digital Forensics  
> **Difficulty:** Easy/Intermediate  
> **Platform:** [TryHackMe](https://tryhackme.com/room/securityfootage)  
> **Author:** Aswin M S (@yourGitHubHandle)

---

## 📖 Scenario

Someone broke into the office and **destroyed the hard drives** that stored the CCTV footage.  
Luckily, a **network capture (`.pcap`)** file from an IP security camera was saved.  
Your mission: **recover the video** from that PCAP and **find the hidden flag**.

---

## 🧰 Tools Used

| Tool       | Use Case                                |
|------------|------------------------------------------|
| `foremost` | Extract (carve) image files from PCAP    |
| `feh`      | View the extracted images as slideshow   |
| Kali Linux | Main OS for forensic analysis            |

---

## 🧠 Step-by-Step Writeup

### 1️⃣ Start with the `.pcap` File

Filename:  
```bash
security-footage-1648933966395.pcap
