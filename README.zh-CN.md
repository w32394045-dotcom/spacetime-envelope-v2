<p align="center">
  <a href="README.md">🇬🇧 English</a> · <a href="README.zh-CN.md">🇨🇳 中文</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/离线运行-无需后端-4f6ef7?style=flat-square" alt="离线运行">
  <img src="https://img.shields.io/badge/加密-AES--256--GCM-10b981?style=flat-square" alt="加密">
  <img src="https://img.shields.io/badge/QR%20拼图-输出-f59e0b?style=flat-square" alt="QR拼图">
  <img src="https://img.shields.io/badge/时间锁-支持-ef4444?style=flat-square" alt="时间锁">
</p>

<h1 align="center">时空数字信封 <sub><sup>v2.4.4</sup></sub></h1>

<p align="center">
  <strong>离线数据加密传输工具</strong>
  <br>
  加密文件、设置时间锁、安全传输 — 纯本地运行，无需后端服务。
</p>

---

## ✨ 功能一览

| 类别 | 功能 | 说明 |
|------|------|------|
| 🔐 | **AES-256-GCM 加密** | 基于密码的文件加密，PBKDF2 密钥派生 |
| 🕐 | **时间锁** | 设置最早/最晚解密时间 — 过期后永久锁定 |
| 🌐 | **NTP 时间校验** | 强制接收方使用 NTP 时间，防止篡改本地时间绕过时间锁 |
| 📤 | **加密发送** | 拖拽文件、设置密码/时间锁、生成数字信封 |
| 📥 | **解密接收** | 导入 .sste 文件或扫描 QR 拼图，解密还原文件 |
| 🧩 | **QR 拼图输出** | 将加密数据拆分为 QR 码，拼合成图片拼图 |
| 📁 | **数字信封 (.sste)** | 紧凑二进制格式，无需扫码 |
| 🖨️ | **打印版 QR 码** | 生成可打印的独立 QR 页面，适合物理传输 |
| 🌙 | **深色模式** | 一键切换 |
| 🌐 | **多语言** | 中文 · English · 日本語 · Русский |

---

## 🚀 快速开始

### 在线使用

直接打开 **[GitHub Pages](https://w32394045-dotcom.github.io/spacetime-envelope-v2/)** 即可使用。

### 本地使用

```bash
git clone https://github.com/w32394045-dotcom/spacetime-envelope-v2.git
cd spacetime-envelope-v2
# 直接用浏览器打开 index.html
```

> 无需安装任何依赖，无需后端服务。

---

> **⚠️ 已知问题与建议**
>
> - **QR 拼图模式目前存在严重识别问题** — 经常完全扫不出来（包括直接上传文件也无法识别）。这是已知问题，短期内无法修复。**建议改用 `.sste` 数字信封格式。**
> - **PNG 输出** 会通过隐写将元数据嵌入图片，存在明文信息残留的风险。如需更严格的隐私保护，**改用 JPEG 或 `.sste`**。
>
> **一句话：用 `.sste` 最省心** — 既可靠又安全。QR 拼图仅在确实需要以图片形式传递数据时使用，且要做好可能识别失败的心理准备。

---

## 📖 使用说明

### 加密发送

1. **选择文件** — 拖拽文件到上传区域
2. **安全设置**（可选）：
   - 设置**解密密码**（AES-256-GCM）
   - 设置**最早/最晚解密时间**（时间锁）
   - 开启 **NTP 校验** 防止接收方修改本地时间绕过限制
3. **选择输出格式**：
   - **数字信封 (.sste)** — 紧凑二进制文件，直接传输
   - **图片拼图 (PNG/JPEG)** — QR 码编码拼图
   - **打印版** — 单个独立 QR 页面
4. **生成并分享** — 下载后发送给接收方

### 解密接收

1. **导入文件** — 拖拽 .sste 文件或 QR 拼图图片
2. **扫描 QR 码**（拼图模式）— 自动识别和组装
3. **验证并解密** — 输入密码（如有），时间锁自动校验
4. **下载还原** — 原始文件恢复

---

## 🧩 工作原理

```
你的文件
    ↓
  [AES-256-GCM]    ← 密码（可选）
  [时间锁]          ← 最早/最晚时间（可选）
    ↓
  加密数据
    ↓
  [数字信封 (.sste)]  OR  [QR 拼图 (PNG/JPEG)]
    ↓
  传输给接收方
    ↓
  [解密] ← 密码（如有） + 时间校验（NTP 可选）
    ↓
  原始文件恢复
```

---

## 🛠️ 技术栈

| 类别 | 技术 |
|------|------|
| **语言** | 纯 HTML + CSS + JavaScript |
| **加密** | Web Crypto API (AES-256-GCM, PBKDF2) |
| **QR 码** | [qrcode.js](https://github.com/davidshimjs/qrcodejs) |
| **NTP** | worldtimeapi.org / timeapi.io |
| **存储** | 浏览器 localStorage |
| **托管** | GitHub Pages |

---

## 🔒 安全说明

- **AES-256-GCM** + PBKDF2 密钥派生（100,000 次迭代）
- **时间锁** 基于时间 KDF — 解密密钥与时间窗口绑定
- **NTP 校验** 防止接收方通过修改系统时间绕过时间锁
- 所有处理**完全在浏览器本地运行** — 文件不会离开你的设备
- 无服务器、无追踪、无数据收集

---

## 📄 License

MIT
