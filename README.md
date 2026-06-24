<div align="center">

<img src="assets/netgeoaudit-logo.png" alt="NetGeoAudit logo" width="120" />

# NetGeoAudit

### Live firewall monitoring &amp; geolocation security audit for Windows

**One window for everything happening on your network — blocked &amp; allowed connections, firewall rules, GeoIP, and a deep system geo-audit. Local databases, no telemetry.**

[![Website](https://img.shields.io/badge/Website-netgeoaudit.com-2563eb?style=for-the-badge)](https://www.netgeoaudit.com/)
[![Download](https://img.shields.io/badge/⬇_Download-Free_Edition-16a34a?style=for-the-badge)](https://www.netgeoaudit.com/)
[![Platform](https://img.shields.io/badge/Windows-10_|_11-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://www.netgeoaudit.com/)

![.NET 10](https://img.shields.io/badge/.NET-10-512BD4?logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-WPF-239120?logo=csharp&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-lightgrey)
![Offline GeoIP](https://img.shields.io/badge/GeoIP-MaxMind_GeoLite2_(offline)-orange)

**🌍 English** · [🇷🇺 Русская версия](README.ru.md)

</div>

---

> ⬇️ **NetGeoAudit is a closed-source product.** This repository is the project's home page and documentation.
> **Downloads (free &amp; licensed editions) are available only from the official site → [www.netgeoaudit.com](https://www.netgeoaudit.com/)**

---

## What is NetGeoAudit?

**NetGeoAudit** is a portable Windows desktop tool that brings **firewall monitoring**, **Windows Firewall rule management**, **network connection logging**, and **IP geolocation auditing** into a single Fluent-design app.

It watches what your machine is actually doing on the network — in real time, at the **firewall / WFP level** (not packet capture) — attributes every connection to a **process**, enriches it with **offline GeoIP** (country, city, ASN, ISP), and lets you **audit, build, and control** Windows Firewall rules. It also runs a deep **system geo-audit**: 50+ scanners that determine which country a machine *really* belongs to.

> **Principle: "local and quiet."** All geolocation databases are bundled and run **offline**. There is **no telemetry**. The app goes online only to verify a license and (optionally) to look up your public IP.

---

## ✨ Features

### 🛰️ Net Log Live — real-time network monitor
Live monitors built on the **Windows Event Log** and the **Windows Filtering Platform (WFP)**, plus a **kernel ETW** capture path:
- **Blocked** and **allowed** connections as they happen
- **RDP session** events and **authentication / logon** events
- **IPv4 &amp; IPv6**, with **process attribution** (which program opened the connection)
- **GeoIP enrichment** on every row (country / city / ASN)
- Smart **time-window de-duplication** with a `×N` repeat badge so noisy events collapse into one line

### 🧱 Firewall Builder — block by country, range, or list
Create **Windows Firewall** rules from:
- **IP ranges** and **CIDR** blocks
- **IP-list files** (paste or import)
- **Country selection** (block whole countries by GeoIP)

Includes a **"Safe Block"** confirmation step and **automatic chunking** to work around the Windows Firewall COM API limits on huge rule sets.

### 🛡️ Control Rules — audit your firewall
A complete audit of existing Windows Firewall rules:
- **5-level risk scoring** for every rule
- **Grouping by application**
- **13 toggle filters** to slice the rule set
- **VirusTotal** integration (SHA-256 hash check) and local **Authenticode** signature verification
- Safe **delete &amp; undo** with an action journal

### 🌐 Win Geo Audit — where is this machine *really* from?
**50+ system scanners** examining locale, registry, WMI, certificates, the **Telephony API / SIM MCC**, Wi-Fi settings, time zone, public IP and more — combined into an **18-level country-resolution chain** that cross-checks every signal.

### 🗺️ Traceroute + GeoIP
- **Per-hop geolocation** of a traceroute using **offline MaxMind GeoLite2** databases
- Standalone **IP lookup**: continent, country, city, **ASN**, **ISP**

### 🧮 Normalizer — clean up IP lists
Parse and normalize IP files: **CIDR**, ranges, and single addresses, with **overlap merging** and split-by-line-count.

---

## 📸 Screenshots

| Net Log Live | Firewall Builder |
|---|---|
| ![Net Log Live — real-time blocked and allowed connections](assets/netlog.jpg) | ![Firewall Builder — block by country, range or list](assets/builder.jpg) |

| Control Rules audit | Live connections + GeoIP |
|---|---|
| ![Control Rules — firewall rule audit with risk scoring](assets/rules.jpg) | ![Connections monitor with GeoIP enrichment](assets/connections.jpg) |

---

## 💻 System requirements

| | |
|---|---|
| **OS** | Windows 10 / 11 (Windows Server 2019/2022 partially supported) |
| **Runtime** | .NET 10 |
| **Privileges** | Administrator rights for WFP monitoring, Event Log access &amp; rule management; some features work without elevation |
| **Format** | Portable — no installer, self-updating |

---

## 💸 Pricing &amp; editions

| | Free edition | Full license |
|---|---|---|
| **Price** | Free, **perpetual** | **5000 ₽** one-time, perpetual |
| **Scope** | Feature-limited | Everything unlocked |
| **Binding** | — | Single machine per key (volume discounts from 5+ licenses) |
| **Updates** | — | All **v1.x** updates included |
| **Commercial use** | — | Allowed under license |

👉 **Get it on [www.netgeoaudit.com](https://www.netgeoaudit.com/)**

---

## 🔒 Privacy

- All geolocation databases (**MaxMind GeoLite2 City + ASN**) are bundled and run **fully offline**
- **No telemetry**, no analytics, no external APIs for core functionality
- Online access only for **license verification** and **optional** public-IP lookup

---

## ❓ FAQ

**Why does it need administrator rights?**
WFP monitoring, Windows Event Log access, and firewall-rule management require elevation. Read-only/utility features run without it.

**How is it different from Wireshark?**
Wireshark decodes packets at the protocol level. NetGeoAudit works at the **firewall / WFP &amp; Event Log level** — it shows which **rule** applied and which **program** owns the connection, enriched with GeoIP — without packet capture.

**Does it phone home?**
No telemetry. Offline databases. It only contacts the network for license checks and optional public-IP lookups.

**Is the source code available?**
No — NetGeoAudit is a proprietary, closed-source product. This repo hosts documentation and links; downloads are on the [official site](https://www.netgeoaudit.com/).

---

## 🧩 Built with

`.NET 10` · `C#` · `WPF` + `WPF-UI 4.x` (Fluent Design) · `CommunityToolkit.Mvvm` (MVVM) · `SQLite` · `MaxMind GeoLite2` (offline GeoIP) · `ETW / TraceEvent` · `Windows Filtering Platform (WFP)`

---

## 🔎 Keywords

Windows firewall monitor · WFP monitoring · Windows Filtering Platform · network connection logger · real-time firewall log · block IP by country · firewall rule builder · Windows Firewall rule audit · firewall risk scoring · GeoIP lookup · IP geolocation · MaxMind GeoLite2 offline · traceroute geolocation · ASN / ISP lookup · netstat alternative · RDP login monitoring · authentication event log · ETW network capture · VirusTotal hash check · Authenticode verification · threat hunting · network security audit · system geo-audit · country detection · portable Windows security tool · no telemetry · IPv4 IPv6 · CIDR normalizer

---

<div align="center">

**[⬇️ Download NetGeoAudit](https://www.netgeoaudit.com/)** · **[🌐 Official website](https://www.netgeoaudit.com/)** · **[🇷🇺 Русское описание](README.ru.md)**

<sub>© NetGeoAudit / byFox. Windows is a trademark of Microsoft. MaxMind &amp; GeoLite2 are trademarks of MaxMind, Inc.</sub>

</div>
