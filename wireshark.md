# 🦈 Beginner's Guide to Wireshark on PC

A step-by-step guide to capturing, filtering, and analyzing network traffic on Windows and Linux using **Wireshark**—100% free and open-source.

---

## 📌 What is Wireshark?

Wireshark is a powerful network packet analyzer. It captures real-time data traveling over your network interface (Wi-Fi or Ethernet) and presents it in a human-readable format.

**Common Uses:**
* Troubleshooting slow internet or app connectivity issues.
* Inspecting background data sent by applications.
* Detecting suspicious network connections or malware traffic.
* Learning how network protocols (HTTP, DNS, TCP, UDP) work.

---

## 🛠️ Step 1: Installation & Setup

1. Download Wireshark from the official website: **[wireshark.org](https://www.wireshark.org/)**.
2. Run the installer and keep default settings.
3. ⚠️ **Important:** During installation, ensure **Npcap** (for Windows) or **Pcap** is checked. Wireshark requires this driver to capture network traffic.
4. Complete installation and restart your computer if prompted.

---

## 🚀 Step 2: How to Capture Network Traffic

1. Open **Wireshark**.
2. On the home screen, you will see a list of network interfaces (e.g., *Wi-Fi*, *Ethernet*, *Local Area Connection*).
3. Look for the interface with a moving wave line (this indicates active traffic).
4. **Double-click your active interface** (usually **Wi-Fi** or **Ethernet**) to start capturing.
5. You will see packets populating the screen in real-time.
6. To stop capturing, click the red **Stop ⏹️** button on the top-left toolbar.

---

## 🔍 Step 3: Essential Wireshark Filters

By default, Wireshark captures thousands of packets per minute. Use the top **Apply a display filter** bar to find what you need.

### 1. Filter by Protocol
* `dns` — Shows all domain lookup requests.
* `http` — Shows unencrypted web traffic.
* `tls` or `ssl` — Shows encrypted web traffic (HTTPS).
* `tcp` or `udp` — Shows traffic using TCP or UDP protocols.

### 2. Filter Outgoing Data (Upload Requests)
http.request.method == "POST"
*(Shows applications sending or uploading data to external servers).*

### 3. Filter by IP Address
* **Specific Source IP:** `ip.src == 192.168.1.1`
* **Specific Destination IP:** `ip.dst == 8.8.8.8`
* **Filter Any IP:** `ip.addr == 192.168.1.5`

### 4. Filter by App Port
* `tcp.port == 80` (Standard HTTP)
* `tcp.port == 443` (Standard HTTPS)
* `udp.port == 53` (DNS requests)

---

## 📊 Step 4: Analyzing Traffic & Finding Heavy Data Users

### Find Top IP Connections:
1. Go to the top menu: **Statistics ➔ Endpoints**.
2. Click on the **IPv4** tab.
3. Click on **Tx Bytes** or **Rx Bytes** to sort by highest sent/received data volume.
4. Copy any suspicious IP address and look it up on [VirusTotal](https://www.virustotal.com) or [AbuseIPDB](https://www.abuseipdb.com).

### Inspect Full Packet Stream (Follow Stream):
1. Right-click any suspicious packet in the main list.
2. Select **Follow ➔ TCP Stream** (or **HTTP Stream**).
3. A readable window will pop up showing the conversation between your PC and the remote server.

### Export Files Captured in Traffic:
1. Go to **File ➔ Export Objects ➔ HTTP** (or SMB/FTP).
2. Browse the list of files transferred over unencrypted traffic.
3. Select a file and click **Save** to inspect it locally.

---

## 💾 Step 5: Saving & Exporting Logs

* To save your captured traffic for later analysis, click **File ➔ Save As...** and save it as a `.pcapng` or `.pcap` file.
* This file can be shared or opened later in Wireshark on any device.

---

## 💡 Quick Tips for Beginners

* **Color Codes:** Wireshark uses colors to highlight packets (e.g., Light Blue = UDP, Light Green = HTTP, Black/Red = Packet errors/TCP Resets).
* **Clear Filter:** Click the **`X`** button inside the filter bar to clear your active filter.
* **Combine Filters:** Use `and` / `or` to combine filters. Example:
  ```text
  ip.addr == 192.168.1.5 and dns

## ⚠️ Important Disclaimer
Use Wireshark only on network connections you own or have explicit permission to monitor.
Sniffing traffic on public Wi-Fi networks without authorization is illegal.
