# 📡 BW16 Dual-Band Wi-Fi Analyzer (Portable Firmware)

[![Firmware Release](https://img.shields.io/github/v/release/mumelanmal/bw16-scanner-firmware?color=00e676&label=Firmware%20Release)](https://github.com/mumelanmal/bw16-scanner-firmware/releases/latest)
[![Target Board](https://img.shields.io/badge/Hardware-Ai--Thinker%20BW16%20(RTL8720DN)-7c4dff)](https://github.com/mumelanmal/bw16-scanner-firmware)
[![Wi-Fi Bands](https://img.shields.io/badge/Wi--Fi-Dual--Band%202.4%20GHz%20%2B%205%20GHz-00b0ff)](https://github.com/mumelanmal/bw16-scanner-firmware)
[![Telegram Support](https://img.shields.io/badge/Telegram-@mumelanmal-26A5E4?logo=telegram&logoColor=white)](https://t.me/mumelanmal)

Turn your pocket-sized **Ai-Thinker BW16 (Realtek RTL8720DN)** into a high-performance **Dual-Band (2.4 GHz & 5 GHz) Wi-Fi Analyzer & Spectrum Scanner**.

Simply plug the board into any 5V USB charger or power bank, connect your smartphone or laptop to its built-in Wi-Fi hotspot, and inspect surrounding wireless networks through a sleek, responsive dark-mode Web Portal — **zero app installation required!**

---

## 📥 Download Ready-to-Flash Firmware (.bin)

No coding or compiling needed! Download the pre-compiled binary files ready for flashing:

| Package | Contents | Direct Link |
| :--- | :--- | :---: |
| **`BW16_DualBand_Scanner_v1.0.0.zip`** | Complete bundle: firmware (`km0_km4_image2.bin`) + bootloader + guide | [**Download (.zip)**](https://github.com/mumelanmal/bw16-scanner-firmware/releases/latest) |
| **`km0_km4_image2.bin`** | Main application firmware image | [**Download (.bin)**](https://github.com/mumelanmal/bw16-scanner-firmware/releases/latest) |

👉 **[View All Official Releases & Changelogs on GitHub](https://github.com/mumelanmal/bw16-scanner-firmware/releases)**

---

## 🔑 How to Purchase & Activate Lifetime License

To prevent mass cloning and support ongoing feature development, each firmware installation is bound to your device's unique hardware MAC address.

1. **Flash the firmware** onto your BW16 board and connect to its Wi-Fi hotspot: `BW16-Scanner-XXXX`.
2. Open your browser and visit: **`http://192.168.1.1`**.
3. The activation screen will display your unique **Device MAC** (e.g., `00:E0:4C:12:34:56`).
4. Click **"Copy MAC"** and send it directly to Telegram:
   
   👉 **[Contact via Telegram: @mumelanmal](https://t.me/mumelanmal)**

5. You will receive your **16-character Lifetime Activation Key** (e.g., `XXXX-XXXX-XXXX-XXXX`).
6. Paste the key into the portal and click **"Activate Now"**.
7. Your device is unlocked **permanently** — the license is written to onboard non-volatile flash and survives all reboots and power disconnections!

---

## ✨ Key Features

* 📶 **Simultaneous Dual-Band Scanning** — Scans both crowded **2.4 GHz** channels (Ch 1–14) and fast, interference-free **5 GHz** channels (Ch 36–165).
* 🔋 **Ultra-Portable & Low Power** — Draws only ~80 mA. Powered all day from any small 5,000 mAh power bank.
* 📱 **Mobile-First Responsive Dashboard** — Fast Single Page Application (SPA) with dark cyberpunk styling, auto-formatting to phones, tablets, and laptops.
* ⚡ **100% Offline Operation** — All assets (HTML/CSS/JS) are hosted locally from the BW16 flash. No internet connection or cloud dependency required.
* 🎯 **Smart Filter Tabs** — Switch views between `All`, `2.4 GHz Only`, `5 GHz Only`, or `Open Networks` with a single tap.
* 📊 **Detailed Telemetry** — Live RSSI signal meters (visual bars + dBm), BSSID router MACs, Channel frequencies, and security protocols (WPA2, WPA3, WEP, Open).
* 🔍 **Instant Search** — Real-time filter by SSID name or manufacturer BSSID.
* 🔌 **Built-in REST API** — Includes `/api/scan` and `/api/status` endpoints for custom automation or Home Assistant integration.

---

## 🚀 Quick Start Guide (3 Steps)

```
[ Power Bank / 5V USB ] ──(USB)──> [ Ai-Thinker BW16 ]
                                          │
                                          ▼ Wi-Fi AP: BW16-Scanner-XXXX
                                [ Smartphone / PC ]
                                          │
                                          ▼ Open Browser
                                   http://192.168.1.1
```

### Step 1: Flash Firmware
1. Connect your BW16 to your computer using a USB data cable.
2. Hold the **Burn** button, press the **Reset** button once, then release Burn.
3. Open **Ameba Image Tool**, select your COM port, choose **`km0_km4_image2.bin`**, and click **Download**.
4. Press **Reset** on the board.

*(Detailed step-by-step flashing guide: [docs/FLASHING_GUIDE.md](docs/FLASHING_GUIDE.md))*

---

### Step 2: Connect to Hotspot
1. Power up the BW16 with any USB adapter or power bank.
2. On your phone or laptop, look for the Wi-Fi network:
   * **SSID:** `BW16-Scanner-XXXX` *(where XXXX is the last 4 characters of your MAC)*
   * **Password:** *(None / Open)*
3. Connect to the network.

---

### Step 3: Launch Dashboard
1. Open any web browser (Chrome, Safari, Firefox, Edge) and visit:
   ```
   http://192.168.1.1
   ```
2. Activate your license using the code from Telegram [@mumelanmal](https://t.me/mumelanmal).
3. Tap **"Start Scan"** to inspect wireless networks around you!

---

## ❓ Frequently Asked Questions (FAQ)

<details>
<summary><b>Does this tool need an internet connection?</b></summary>
No. The analyzer is 100% self-contained. The web server and scanner run entirely on the RTL8720DN chip.
</details>

<details>
<summary><b>If I unplug the USB or battery, do I have to activate again?</b></summary>
No. Your license key is stored in the BW16 internal non-volatile Flash memory with hardware-checksum validation. It remains permanently activated across all power cycles.
</details>

<details>
<summary><b>Why is there a brief 1-2 second pause when scanning?</b></summary>
During scanning, the Wi-Fi transceiver hops across all 2.4 GHz and 5 GHz radio channels to capture beacons. A brief 1–2 second pause while the scan completes is normal transceiver behavior.
</details>

<details>
<summary><b>Can I re-flash or update the firmware later?</b></summary>
Yes! Since your license key is stored in a dedicated flash sector, updating to newer firmware releases (`.bin`) will preserve your activation status as long as you flash the same module.
</details>

---

## 💬 Support & Inquiries

For license purchases, bulk inquiries, or technical support:
* **Telegram:** [@mumelanmal](https://t.me/mumelanmal)
* **GitHub Issues:** [Report a Bug / Feature Request](https://github.com/mumelanmal/bw16-scanner-firmware/issues)
