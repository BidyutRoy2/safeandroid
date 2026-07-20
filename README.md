# 🛡️ Beginner's Guide: Find Data-Stealing Apps on Android & Remove Them

Is your phone leaking private data in the background? This easy, step-by-step guide will show you how to **track background activity**, **find sneaky apps**, **block them**, and **delete unwanted apps**—even without rooting your phone or having advanced technical skills!

---

## 📌 Quick Summary: How This Works

1. **Record:** Use **PCAPdroid** on your phone to record all internet activity into a file.
2. **Inspect:** Open that file on a PC using **Wireshark** to see which app sent data to suspicious servers.
3. **Block:** Stop the offending app's internet access instantly using **RethinkDNS**.
4. **Delete:** Permanently remove the bad app using **Shizuku + Canta**.

---

## 🛠️ Step 0: Download the Free Tools

All tools used in this guide are open-source and free:

* 📱 **[PCAPdroid](https://play.google.com/store/apps/details?id=com.emanuelef.remote_pdb):** Records your phone's internet traffic.
* 💻 **[Wireshark](https://www.wireshark.org/):** Free software for your PC/Ubuntu to inspect recorded files.
* 🛡️ **[RethinkDNS](https://play.google.com/store/apps/details?id=com.celzero.bravedns):** A powerful firewall to block internet access for specific apps.
* ⚡ **[Shizuku](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api):** Gives special permissions to delete system apps without root.
* 🗑️ **[Canta](https://f-droid.org/packages/org.schabi.newpipe/):** The app remover that works with Shizuku. *(Search inside F-Droid to install)*.

---

## 🚀 Step-by-Step Instructions

### 📥 Step 1: Record Your Phone's Activity (PCAPdroid)

> **Goal:** Catch background activity while your phone is idle or in use.

1. Open **PCAPdroid**.
2. Tap the **Settings** ⚙️ icon.
3. Tap **Traffic dump** and select **`PCAP file`**.
4. Go back to the main screen and tap the **Play ▶️** button.
5. If Android asks for **VPN permission**, tap **Allow**.
6. **Leave your phone running** for 1 to 6 hours (you can lock your screen or use your phone normally).
7. Tap **Stop ⏹️**. A `.pcap` file is now saved in your phone's `Downloads` or `Documents` folder.

---

### 🔍 Step 2: Analyze the File on Your Computer (Wireshark)

> **Goal:** Find out which app sent your data and where it went.

1. Send the saved `.pcap` file to your PC or Laptop.
2. Open the `.pcap` file in **Wireshark**.
3. **Check secret data uploads:** In the top search bar, type:
   ```text
   http.request.method == "POST"
*(This shows apps sending data out to external servers).*
4. **Find heavy data users:** Click **Statistics** (at the top menu) ➔ **Endpoints** ➔ **IPv4**. Click on **Tx Bytes** to sort from highest to lowest.
5. **Check suspicious IPs:** If you see an unknown IP address sending large amounts of data, copy it and paste it into [VirusTotal.com](https://www.virustotal.com) to check if it's dangerous.

---

### 🛑 Step 3: Block the Sneaky App Immediately (RethinkDNS)

> **Goal:** Stop bad apps from connecting to the internet without deleting them yet.

1. Open **RethinkDNS** and tap **Start**.
2. Go to the **Apps** tab at the bottom.
3. Find the suspicious app on the list.
4. Tap both the **Wi-Fi** and **Mobile Data** icons next to it so they turn into **Red Crosses (❌)**.

*🎉 **Result:** The app is now completely cut off from the internet and cannot leak any data!*

---

### 🗑️ Step 4: Permanently Delete the Bad App (Shizuku + Canta)

> **Goal:** Uninstall bloatware or hidden spyware without rooting or connecting to a PC.

1. Go to your phone's **Settings ➔ Developer Options** and turn on **Wireless Debugging**.
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
* 🔓 **Compromised Accounts:** If your Google or social media password is weak, hackers can access your data from another device.

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
