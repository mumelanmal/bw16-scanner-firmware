# 📖 BW16 Dual-Band Wi-Fi Analyzer - Flashing Guide

This step-by-step tutorial guides you through uploading (*flashing*) the pre-compiled binary firmware to your **Ai-Thinker BW16 (Realtek RTL8720DN)** development board.

---

## 1. Hardware Requirements

* **Ai-Thinker BW16 Board** (RTL8720DN module on breakout / dev board).
* **USB Data Cable** (Micro-USB or Type-C, ensure it supports data transfer, not power-only).
* **Computer/Laptop** (Windows 10/11, Linux, or macOS).

---

## 2. Firmware Files Overview

From the [Releases](https://github.com/mumelanmal/bw16-scanner-firmware/releases) section, download `BW16_DualBand_Scanner_v1.0.0.zip` or individual files:

* **`km0_km4_image2.bin`** *(Required)*: The main dual-band analyzer application image (Flash Image 2).
* **`km0_boot_all.bin`** *(Optional / Factory Restore)*: Cortex-M0 system bootloader.
* **`km4_boot_all.bin`** *(Optional / Factory Restore)*: Cortex-M33 application bootloader.

---

## 3. Entering Bootloader / Download Mode on BW16

Before flashing, your BW16 must be placed into **UART Download Mode**:

1. Plug the BW16 into your computer via USB.
2. **Press and hold** the **Burn / Boot** button (marked as `Burn` or `B` on the board).
3. While still holding the Burn button, **press and release** the **RST (Reset)** button once.
4. **Release** the Burn button.
5. Your BW16 is now in Download Mode (the green LED will typically remain off or blink once).

---

## 4. Flashing via Ameba Image Tool (Recommended)

1. **Download the Ameba Image Tool** (official utility from Realtek AmebaD):
   * Included in the Ameba Arduino package or downloadable from Realtek Ameba IoT docs.
2. **Open Ameba Image Tool**.
3. **Select your COM Port** (e.g., `COM3`, `COM5`, or `/dev/ttyUSB0`).
4. Set the Baudrate to **`115200`** (or **`1500000`** for high-speed flashing).
5. Switch to the **Download** tab:
   * Check **Image 2 (Flash)** and browse to select **`km0_km4_image2.bin`**.
   * *(If flashing a completely fresh/blank module)*: Also load `km0_boot_all.bin` and `km4_boot_all.bin` into their respective bootloader fields.
6. Click the **Download** button.
7. Wait until the progress bar reaches **100% (Success)**.
8. Press the **RST (Reset)** button on your BW16 to boot into normal operation.

---

## 5. Verification & First Boot

1. Once rebooted, the BW16 will start broadcasting its own Wi-Fi Access Point:
   * **SSID:** `BW16-Scanner-XXXX` *(where XXXX is the last 4 digits of your device's MAC)*
   * **Password:** *(None / Open Network)*
2. Connect your smartphone or laptop to `BW16-Scanner-XXXX`.
3. Open your browser and navigate to:
   ```
   http://192.168.1.1
   ```
4. Follow the on-screen instructions to activate your lifetime license!

---

## 6. Troubleshooting

* **COM Port not detected:** Ensure your USB cable is a genuine data cable and you have installed the USB-to-UART driver (CH340, CP2102, or FTDI depending on your board's USB chip).
* **Download Failed / Timeout:** Repeat Step 3 (Hold Burn -> Click Reset -> Release Burn) to ensure the board is in download mode, and verify the correct COM port is selected.
