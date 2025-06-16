# 🕵️‍♂️ TryHackMe - Security Footage

> **Room Link:** [https://tryhackme.com/room/securityfootage](https://tryhackme.com/room/securityfootage)  
> **Category:** Digital Forensics  
> **Difficulty:** Easy/Intermediate  
> **Author:** Aswin M S 

---

## 📖 Scenario

An intruder broke into our office and physically destroyed the hard drives that contained the security footage.  
However, a `.pcap` (packet capture) file was collected from the network. The IP camera most likely streamed video over the network — your job is to **analyze this PCAP file**, **recover the video footage**, and **identify any flag or clue** from it.

---

## 🧰 Tools Used

| Tool         | Purpose                                  |
|--------------|-------------------------------------------|
| `foremost`   | Carve/extract image files from PCAP       |
| `feh`        | Display images as slideshow (like video)  |
| `Kali Linux` | OS for analysis and tool execution        |

---

## 🪜 Step-by-Step Procedure

### ✅ Step 1: Analyze the PCAP File

- Open the provided `.pcap` file:
  ```
  security-footage-1648933966395.pcap
  ```
- Since it's from a security camera, the data is likely in **MJPEG** format — each frame as a `.jpg`.

---

### ✅ Step 2: Extract Images from PCAP using Foremost

- Run the `foremost` tool:
  ```bash
  foremost -i security-footage-1648933966395.pcap -o extracted/
  ```
- This creates a folder: `extracted/jpeg/` that contains all `.jpg` images (video frames).

---

### ✅ Step 3: Install feh to View Images as a Slideshow

If not installed already, install `feh`:

```bash
sudo apt update
sudo apt install feh
```

> ⚠️ If you get mirror errors, update your source list:
```bash
sudo nano /etc/apt/sources.list
```
Replace content with:
```
deb http://http.kali.org/kali kali-rolling main non-free contrib
```
Then run:
```bash
sudo apt update --fix-missing
```

---

### ✅ Step 4: View the Extracted Frames as a Video

- Navigate into the JPEG folder:
  ```bash
  cd extracted/jpeg
  ```

- Preview the images as a slideshow:
  ```bash
  feh --slideshow-delay 0.1 *.jpg
  ```

This simulates the video feed. Carefully inspect each frame for visual clues (like notes, whiteboards, stickers, etc.).

---

### ✅ Step 5: Investigate for Clues or Flag

- Go through the frames slowly.
- Look out for things written on a whiteboard or screen.
- One of the frames should contain a flag or valuable evidence.

---

## 📚 Skills & Concepts Learned

- 📡 How MJPEG (Motion JPEG) streams are transferred over a network
- 🛠️ Carving files from `.pcap` captures using `foremost`
- 🖼️ Using `feh` to simulate video from image sequences
- 🔍 Real-world digital forensics process
- ⚙️ Basic Linux troubleshooting (mirror errors, installing tools)
- 📁 Directory navigation and file organization for forensic evidence

---

## 🎥 Bonus Tip: Convert Frames into a Video File

Use `ffmpeg` to convert the image sequence into a `.mp4`:

```bash
ffmpeg -framerate 10 -pattern_type glob -i '*.jpg' -c:v libx264 -pix_fmt yuv420p output.mp4
```

---

## 🔗 Connect With Me

- **GitHub**: [Git Hub](https://github.com/ASWINMS07)
- **TryHackMe**: [TryHackMe](https://tryhackme.com/p/AswinMS)
- **LinkedIn**: [Linkedin](https://www.linkedin.com/in/msaswin07/)

---

> 💀 Forensics Forever.  
> 🚀 TryHackMe Journey: Logged & Loaded.
