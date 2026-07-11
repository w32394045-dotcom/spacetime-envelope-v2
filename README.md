<p align="center">
  <a href="README.zh-CN.md">🇨🇳 中文</a> · <a href="README.md">🇬🇧 English</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Offline-No%20Backend-4f6ef7?style=flat-square" alt="Offline">
  <img src="https://img.shields.io/badge/Encryption-AES--256--GCM-10b981?style=flat-square" alt="Encryption">
  <img src="https://img.shields.io/badge/QR%20Puzzle-Output-f59e0b?style=flat-square" alt="QR Puzzle">
  <img src="https://img.shields.io/badge/Time%20Lock-Supported-ef4444?style=flat-square" alt="Time Lock">
</p>

<h1 align="center">Spacetime Envelope <sub><sup>v2.4.4</sup></sub></h1>

<p align="center">
  <strong>Offline Encrypted File Transfer Tool</strong>
  <br>
  Encrypt files, set time locks, transfer securely — fully offline, no backend required.
</p>

---

## ✨ Features

| Icon | Feature | Description |
|------|---------|-------------|
| 🔐 | **AES-256-GCM Encryption** | Password-based file encryption with PBKDF2 key derivation |
| 🕐 | **Time Lock** | Set earliest/latest decryption time — file locks permanently after expiry |
| 🌐 | **NTP Verification** | Force receiver to use NTP time, preventing local time tampering |
| 📤 | **Encrypt & Send** | Drag & drop files, set password/time lock, generate digital envelope |
| 📥 | **Decrypt & Receive** | Import .sste file or scan QR puzzles to decrypt and restore |
| 🧩 | **QR Puzzle Output** | Split encrypted data into QR codes, assembled into image puzzles |
| 📁 | **Digital Envelope (.sste)** | Compact binary format, no scanning needed |
| 🖨️ | **Printable QR Codes** | Generate print-ready individual QR pages for physical transfer |
| 🌙 | **Dark Mode** | Built-in theme toggle |
| 🌐 | **Multi-Language** | 中文 · English · 日本語 · Русский |

---

## 🚀 Quick Start

### Online

Open **[GitHub Pages](https://w32394045-dotcom.github.io/spacetime-envelope-v2/)** directly in your browser.

### Local

```bash
git clone https://github.com/w32394045-dotcom/spacetime-envelope-v2.git
cd spacetime-envelope-v2
# Open index.html in your browser
```

> No dependencies to install, no server required.

---

> **⚠️ Known Issues & Recommendations**
>
> - **QR puzzle scanning** can be unreliable across different devices and lighting conditions — **we recommend using the `.sste` envelope format** for the most reliable transfer experience.
> - **PNG output** embeds metadata using steganography, which may leave readable plaintext traces in the encoded image. For better privacy, **use JPEG or `.sste` instead**.
>
> Bottom line: `.sste` is the most robust and privacy-preserving option. Use QR puzzles only when visual/image-based transfer is unavoidable.

---

## 📖 Usage

### Encrypt & Send

1. **Select Files** — Drag & drop files into the upload zone
2. **Security Settings** (optional):
   - Set a decryption **password** (AES-256-GCM)
   - Set **earliest/latest decryption time** for time lock
   - Enable **NTP verification** to prevent local time bypass
3. **Choose Output Format**:
   - **Digital Envelope (.sste)** — compact binary file
   - **Image Puzzle (PNG/JPEG)** — QR-encoded puzzle
   - **Print Version** — individual QR pages
4. **Generate & Share** — download and transfer to recipient

### Decrypt & Receive

1. **Import File** — Drag & drop .sste file or QR puzzle images
2. **Scan QR Codes** (for puzzle mode) — auto-detect and assemble
3. **Verify & Decrypt** — enter password if required, time lock auto-validates
4. **Download** — original files restored

---

## 🧩 How It Works

```
Your File
    ↓
  [AES-256-GCM] ← Password (optional)
  [Time Lock]    ← Earliest/Latest time (optional)
    ↓
  Encrypted Data
    ↓
  [Digital Envelope (.sste)]  OR  [QR Puzzle (PNG/JPEG)]
    ↓
  Transfer to recipient
    ↓
  [Decrypt] ← Password (if set) + Time validation (NTP optional)
    ↓
  Original File Restored
```

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|-----------|
| **Language** | Vanilla HTML + CSS + JS |
| **Encryption** | Web Crypto API (AES-256-GCM, PBKDF2) |
| **QR Code** | [qrcode.js](https://github.com/davidshimjs/qrcodejs) |
| **NTP** | worldtimeapi.org / timeapi.io |
| **Storage** | Browser localStorage |
| **Hosting** | GitHub Pages |

---

## 🔒 Security

- **AES-256-GCM** with PBKDF2 key derivation (100,000 iterations)
- **Time Lock** uses time-based KDF — decryption key depends on the time window
- **NTP Verification** prevents receiver from bypassing time lock by changing system clock
- All processing is **fully offline** in your browser — your files never leave your device
- No server, no tracking, no data collection

---

## 📄 License

MIT
