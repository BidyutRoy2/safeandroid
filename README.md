# 🛡️ Beginner's Guide: Find Data-Stealing Apps on Android & Remove Them

Is your phone leaking private data in the background? This easy, step-by-step guide will show you how to **track background activity**, **find sneaky apps**, **block them**, and **delete unwanted apps**—**100% using your Android phone (No PC or Root required!)**.

---

## 📌 Quick Summary: How This Works

1. **Record & Inspect:** Capture and analyze your phone's internet traffic using **Reqable** / **PCAPdroid** directly on Android (or **Wireshark** on PC).
2. **Identify:** Find which app is sending data to suspicious external servers.
3. **Block:** Stop the offending app's internet access instantly using **RethinkDNS**.
4. **Delete:** Permanently remove the bad app using **Shizuku + Canta**.

---

## 🛠️ Step 0: Download the Free Tools

All tools used in this guide are open-source or free to use:

* 📱 **[PCAPdroid](https://play.google.com/store/apps/details?id=com.emanuelef.remote_pdb):** Captures and tracks live network traffic on Android.
* 🔍 **[Reqable](https://play.google.com/store/apps/details?id=com.reqable.android):** Inspects HTTP/HTTPS traffic directly on Android without needing a PC.
* 💻 **[Wireshark](https://www.wireshark.org/):** *(Optional)* For detailed PC/Laptop analysis.
* 🛡️ **[RethinkDNS](https://play.google.com/store/apps/details?id=com.celzero.bravedns):** A local firewall to block internet access for specific apps.
* ⚡ **[Shizuku](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api):** Grants special permissions to delete system apps without root.
* 🗑️ **[Canta](https://f-droid.org/packages/org.schabi.newpipe/):** The app uninstaller that works with Shizuku *(Search inside F-Droid)*.

---

## 🚀 Step-by-Step Instructions

### 📥 Step 1: Record Your Phone's Activity (PCAPdroid)

> **Goal:** Catch background activity while your phone is idle or in use.

1. Open **PCAPdroid**.
2. Tap the **Settings** ⚙️ icon.
3. Choose your dump option:
   * **`No dump`** (If analyzing live inside PCAPdroid or Reqable on Android).
   * **`PCAP file`** (If saving a log file to analyze later).
4. Return to the main screen and tap **Start ▶️** (Grant VPN permission).
5. Leave your phone running for **1 to 6 hours**.
6. Tap **Stop ⏹️**.

---

### 🔍 Step 2: Analyze Traffic (No PC Needed!)

> **Goal:** Find out which app sent your data and where it went.

#### Option A: Using Android Only (No PC Needed) 📱
1. **Live Inspection in PCAPdroid:**
   * Go to the **Connections** tab inside PCAPdroid.
   * Look for unknown apps or services sending unexpectedly large amounts of data (KB/MB).
   * Tap any suspicious connection to inspect its destination domain and IP address.
2. **Deep Inspection using Reqable:**
   * Open **Reqable** and tap **Start**.
   * Filter the connection list by **POST** requests (which indicates outgoing data/uploads).
   * Copy any unknown IP or domain and paste it into [VirusTotal.com](https://www.virustotal.com) to check for malware/spyware flags.

#### Option B: Using a Computer (Wireshark) 💻
1. Transfer the saved `.pcap` file to your PC.
2. Open it in **Wireshark**.
3. Type `http.request.method == "POST"` in the top filter bar.
4. Go to **Statistics ➔ Endpoints ➔ IPv4** and sort by **Tx Bytes** to spot heavy data uploads.

---

### 🛑 Step 3: Block the Sneaky App Immediately (RethinkDNS)

> **Goal:** Cut off internet access for suspicious apps without deleting them yet.

1. Open **RethinkDNS** and tap **Start**.
2. Go to the **Apps** tab at the bottom.
3. Locate the suspicious app on the list.
4. Tap both the **Wi-Fi** and **Mobile Data** icons until they turn into **Red Crosses (❌)**.

*🎉 **Result:** The app is now completely cut off from the internet and cannot leak any data!*

---

### 🗑️ Step 4: Permanently Delete the Bad App (Shizuku + Canta)

> **Goal:** Uninstall bloatware or hidden spyware without rooting or connecting to a PC.

1. Go to **Settings ➔ Developer Options** and enable **Wireless Debugging**.
2. Open **Shizuku**, tap **Pairing**, and enter the 6-digit code provided by Wireless Debugging.
3. Tap **Start** inside Shizuku.
4. Open **Canta** and grant it permission to connect with Shizuku.
5. Search for the suspicious app name in Canta.
6. Select the app and tap the **Trash / Uninstall** button.

---

## ❓ Can You Be 100% Safe From Hackers?

**Honest Answer:** No security setup in the world is 100% unhackable. While this guide protects you against **90–95% of common malware and privacy leaks**, here is why 100% security doesn't exist:

* 🎣 **Phishing Scams:** If you manually type your password into a fake website, network monitoring cannot save you.
* 🐛 **System Vulnerabilities (Zero-Days):** Undiscovered bugs in Android or hardware can sometimes bypass user-level firewalls.
* 🔓 **Compromised Accounts:** Weak passwords or compromised cloud accounts can lead to data loss regardless of device isolation.

---

## 💡 4 Golden Rules for Maximum Daily Protection

Combine this guide with these 4 simple habits to stay virtually bulletproof:

1. 🔐 **Turn on 2FA:** Always enable **Two-Factor Authentication** on all your email and social media accounts using an authenticator app (like Aegis or Google Authenticator).
2. 🚫 **Avoid Modded/Cracked APKs:** Never install modified (MOD) apps or games from random websites. Only use Google Play Store or F-Droid.
3. 🔄 **Keep System Updated:** Always install the latest Android security patches.
4. ⚙️ **Review Permissions:** Regularly check which apps have access to your Location, Contacts, Microphone, and Camera.

---

## ⚠️ Important Safety Notice

* **Do not delete core system apps** (like `com.android.systemui` or Google Play Services) in Canta, as this may cause your phone to reboot continuously.
* Always search the package name online if you are unsure what an app does before uninstalling it.

---

## 📄 License

This guide is open-source under the [MIT License](LICENSE). Feel free to share and adapt!
