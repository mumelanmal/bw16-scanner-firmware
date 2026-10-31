# BW16 Dual-Band Wi-Fi Analyzer - Flashing & Setup Guide

This guide provides step-by-step instructions for flashing the pre-compiled binary firmware to your **Ai-Thinker BW16 (Realtek RTL8720DN)** board.

---

## 1. Hardware Requirements
1. **Ai-Thinker BW16 Board** (RTL8720DN module / breakout dev board).
2. **USB Data Cable** (Micro-USB or Type-C; ensure it supports data transfer, not power-only).
3. **Computer/Laptop** (Windows 10/11, Linux, or macOS).

---

## 2. Firmware Binary Files
This release package includes:
* **`km0_km4_image2.bin`** *(Required)*: The main Dual-Band Wi-Fi Analyzer application firmware.
* **`km0_boot_all.bin`** *(Optional / Factory)*: Cortex-M0 system bootloader.
* **`km4_boot_all.bin`** *(Optional / Factory)*: Cortex-M33 application bootloader.

---

## 3. Flashing Steps via Ameba Image Tool

### Step A: Enter Download / Bootloader Mode
1. Plug the BW16 board into your computer's USB port.
2. **Press and hold** the **Burn** button (labeled `Burn` or `B`).
3. While still holding **Burn**, press and release the **RST (Reset)** button once.
4. **Release** the **Burn** button.
5. The BW16 is now in **UART Bootloader / Download Mode** (the green LED will stay off or blink once).

### Step B: Flash Firmware with Ameba Image Tool
1. Open **Ameba Image Tool** (Windows utility provided by Realtek).
2. Select your device's **COM Port** (e.g., `COM3`, `COM5`, or `/dev/ttyUSB0`).
3. Set Baudrate to **`115200`** or **`1500000`** (1.5M for high-speed flashing).
4. Navigate to the **Download** tab:
   - Check **Image 2 (Flash)** and browse to select **`km0_km4_image2.bin`**.
   - *(Optional - only needed if board flash is completely empty)*: Also select `km0_boot_all.bin` and `km4_boot_all.bin` into bootloader slots.
5. Click **Download** and wait until the progress bar reaches **100% (Success)**.
6. Once finished, press the **RST (Reset)** button on your BW16 to boot into normal operation.

---

## 4. Connecting & Accessing Dashboard
1. After rebooting, the BW16 will broadcast its Wi-Fi Access Point:
   - **SSID:** `BW16-Scanner-XXXX` *(where XXXX is the last 4 hex digits of your MAC)*
   - **Password:** None (Open Network for instant, seamless connection)
2. Connect your smartphone or laptop to `BW16-Scanner-XXXX`.
3. Open any web browser (Chrome, Safari, Firefox, Edge) and navigate to:
   ```
   http://192.168.1.1
   ```
4. If this is your first time powering on:
   - The **Device Activation** page will display your unique **Device MAC**.
   - Copy your Device MAC and send it to our Telegram channel: **[@mumelanmal](https://t.me/mumelanmal)**.
   - Enter your 16-character Lifetime Activation Key and click **"Activate Now"**.
5. Once activated, your device is permanently unlocked and the full-featured **BW16 Dual-Band Wi-Fi Analyzer** dashboard will load immediately!

---

## 5. Support & Inquiries
- **Telegram:** [@mumelanmal](https://t.me/mumelanmal)
- **GitHub Repository:** [mumelanmal/bw16-scanner-firmware](https://github.com/mumelanmal/bw16-scanner-firmware)
