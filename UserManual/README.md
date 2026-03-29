# SmallTV Max — Setup Guide

**Firmware v2.4.13** &nbsp;·&nbsp; [GitHub Repository](https://github.com/mikefromdot/SmallTV-Max)

---

## Contents

1. [Power On & First Boot](#1-power-on--first-boot)
2. [Connect to SmallTV Max Wi-Fi](#2-connect-to-smalltv-max-wi-fi)
3. [Open the Setup Page](#3-open-the-setup-page)
4. [Enter Your Wi-Fi Credentials](#4-enter-your-wi-fi-credentials)
5. [Access the Web Interface](#5-access-the-web-interface)
6. [Using the Web Interface](#6-using-the-web-interface)
7. [Touch Controls](#7-touch-controls)
8. [Adding GIF Files](#8-adding-gif-files)
9. [Firmware Updates](#9-firmware-updates)
10. [Troubleshooting](#troubleshooting)

---

## 1. Power On & First Boot

Plug the USB-C cable into the device and a power source. The SmallTV Max boots in a few seconds.

**What you'll see on the screen:**

```
┌─────────────────────┐
│     SmallTV Max     │  ← orange header
│                     │
│       [icon]        │
│                     │
│     SmallTV Max     │
│   JC3248W535EN      │
│                     │
│  ▓▓▓▓▓▓▓▓▓▓░░░░░   │  ← boot progress bar
│                     │
│      FW 2.4.13      │
│      Starting…      │
└─────────────────────┘
```

> **ℹ️ SD Card Note**
> If you insert an SD card it must be formatted as **FAT32**. Cards larger than 32 GB are often formatted exFAT by default — use your computer to reformat as FAT32 first. If the wrong format is detected, the device will show an error and continue using internal storage instead.

---

## 2. Connect to SmallTV Max Wi-Fi

If no Wi-Fi has been saved, the device enters **Setup Mode** and broadcasts its own Wi-Fi network.

**What you'll see on the screen:**

```
┌─────────────────────┐
│      Setup Mode     │  ← orange header
│                     │
│  Step 1: Connect    │
│  ┌───────────────┐  │
│  │  SmallTV Max  │  │  ← Wi-Fi network name
│  └───────────────┘  │
│  ─────────────────  │
│  Step 2: Open to    │
│  ┌───────────────┐  │
│  │  192.168.4.1  │  │  ← browser address
│  └───────────────┘  │
│  ─────────────────  │
│  Step 3: Enter your │
│  credentials & save │
│                     │
│      [QR Code]      │  ← scan for User Manual
│       Read Me       │
└─────────────────────┘
```

On your phone or computer, open **Wi-Fi Settings** and connect to the network named **SmallTV Max**. No password is required.

| Device | Instructions |
|--------|-------------|
| 📱 **iPhone / Android** | A browser may open automatically. If not, open Safari or Chrome and go to `192.168.4.1` |
| 💻 **Windows** | Navigate manually to `http://192.168.4.1` — the captive portal does not appear automatically on Windows by design |
| 🍎 **Mac** | A browser should open automatically. If not, navigate to `http://192.168.4.1` |

> **📖 Read Me QR Code**
> Point your phone camera at the QR code on the screen to open the full online user manual on GitHub.

---

## 3. Open the Setup Page

Open your browser and navigate to:

```
http://192.168.4.1
```

The SmallTV Max web interface will load showing the Wi-Fi setup form.

---

## 4. Enter Your Wi-Fi Credentials

Find the **Wi-Fi** card in the web interface and fill in:

1. **Network name (SSID)** — the exact name of your home Wi-Fi, including capital letters
2. **Password** — your Wi-Fi password. Leave blank if your network has no password
3. **Hostname** *(optional)* — a friendly name for the device on your network, e.g. `smalltv-max`. Defaults to `smalltv-max` if left empty
4. **Click Save & Connect** — the device saves your credentials and reboots

> **⚠️ Connection drop**
> Your browser will lose connection when the device leaves Setup Mode. Wait about 15 seconds, reconnect your computer to your **home** Wi-Fi, then continue to Step 5.

---

## 5. Access the Web Interface

Once connected to your home network, the device is accessible via:

| Method | Address |
|--------|---------|
| **Hostname** | `http://smalltv-max.local` |
| **IP address** | `http://192.168.1.x` (find it on your router or on the device's Info screen) |

> **💡 Tip:** Bookmark the address in your browser for quick access in future.

After connecting successfully, the device screen shows the clock and the IP address briefly before switching to normal operation.

---

## 6. Using the Web Interface

The web interface gives you full control over the device from any browser on your network.

| Section | What it does |
|---------|-------------|
| **Wi-Fi** | Change the connected network, password, or device hostname |
| **Clock & NTP** | Set your NTP server and timezone so the clock shows correct local time |
| **Weather** | Enter a free OpenWeatherMap API key and your city name. Choose metric or imperial units |
| **Display Mode** | Switch between GIF, Clock, Info, and Weather modes |
| **Brightness** | Drag the slider to adjust screen brightness. Setting is saved automatically |
| **GIF Manager** | Upload GIF files, set display duration for each, and rescan storage |
| **Firmware Update** | Check for and install updates from GitHub with one click |
| **Device** | Reboot, Factory Reset, or Format SD Card |

---

## 7. Touch Controls

The touchscreen lets you control the device without opening a browser.

| Gesture | Action |
|---------|--------|
| 👆 **Tap top half** | Increase brightness |
| 👇 **Tap bottom half** | Decrease brightness |
| 👉 **Swipe right** | Next display mode |
| 👈 **Swipe left** | Previous display mode |

**Display modes** cycle through: **GIF → Clock → Info → Weather** (Weather only appears if configured). Your selected mode is remembered across reboots.

---

## 8. Adding GIF Files

The GIF player supports animated GIF files stored on an SD card (recommended) or internal storage. Up to **32 GIF slots** are supported.

### Option A — SD Card (recommended)

1. Format the SD card as **FAT32**
2. Create a folder named `/gifs` on the card
3. Copy your `.gif` files into the `/gifs` folder
4. Insert the card into the device and reboot
5. The device scans the card automatically on startup

### Option B — Upload via Web UI

1. Open the **GIF Manager** section in the web interface
2. Click **Choose File** and select a `.gif` file
3. Click **Upload**
4. The device rescans storage automatically after each upload

### Tips for best results

- GIFs display best at or near **320 × 480 pixels** (portrait orientation)
- Smaller GIFs are centred on a black background
- Aim for **under 10 MB per file** for smooth playback
- In the GIF Manager, set duration to **0** to loop a GIF indefinitely, or set a number of seconds before it advances to the next

---

## 9. Firmware Updates

SmallTV Max checks for firmware updates automatically and lets you install them from the web interface.

### Automatic update flow

1. **60 seconds** after connecting to Wi-Fi, the device silently checks GitHub for a newer version
2. This check repeats every **24 hours**
3. If an update is found, an **amber banner** appears in the Firmware Update section:

```
┌─────────────────────────────────────────────────────────┐
│ ⬆️  Update available: v2.5.0              [⚡ Install]  │
└─────────────────────────────────────────────────────────┘
```

4. Click **Install** — the device downloads and flashes the firmware
5. A full-screen progress overlay appears — **do not power off during this process**
6. The device reboots and the page reloads automatically

### Manual firmware update

If you have a `.bin` file to flash manually:

1. Scroll to **Manual Firmware Update** in the Firmware Update section
2. Click **Choose File** and select your `firmware-x.x.x.bin`
3. Click **Flash**
4. Wait for the progress bar to reach 100% — the full-screen overlay will appear
5. The page reloads automatically once complete

> **🔒 Settings are always preserved**
> Wi-Fi, NTP, weather, brightness, display mode, and GIF durations are stored in NVS (non-volatile storage) and survive all firmware updates.

---

## Troubleshooting

### Can't reach 192.168.4.1
Make sure you are connected to the **SmallTV Max** Wi-Fi network, not your home network. On Windows, navigate manually — the captive portal does not appear automatically.

### Device won't connect to my Wi-Fi
Double-check the SSID and password are exactly correct, including capitalisation. The device will fall back to Setup Mode and broadcast its network again if connection fails.

### SD card not recognised
The card must be formatted as **FAT32**. Cards larger than 32 GB are usually formatted exFAT by default — use your computer's Disk Utility (Mac) or Format tool (Windows) to reformat as FAT32.

### Weather not showing
Ensure you have a valid [OpenWeatherMap API key](https://openweathermap.org/api) (free tier works), a valid city name e.g. `London,UK`, and that Weather is **enabled** in the web interface.

### Clock shows wrong time
Check the NTP settings in the web interface. Set the correct POSIX timezone string for your region. The device requires an active internet connection to sync time via NTP.

### Factory Reset
In the **Device** section of the web interface, click **Factory Reset**. This clears all saved settings (Wi-Fi, NTP, weather, brightness, mode) and reboots into Setup Mode. GIF files on the SD card are **not** affected.

---

*SmallTV Max Firmware v2.4.13 · [github.com/mikefromdot/SmallTV-Max](https://github.com/mikefromdot/SmallTV-Max) · MIT License + Commons Clause*
