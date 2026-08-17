<div align="center">

# 🛰️ Network Monitor (NetMon)

**Advanced network monitoring, Game Boost & automation toolkit — built with Python + CustomTkinter**

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)
![License](https://img.shields.io/badge/License-MIT-green)
![Version](https://img.shields.io/badge/Version-3.4-cyan)

</div>

A single-file desktop app that turns your network into a live dashboard: real-time throughput charts,
per-process traffic, connection tables, speed & ping tests, port / IP scanners, DNS tools, Geo-IP
lookups, daily HTML/PDF reports — plus a **Game Boost** section (QoS-style priority, power plan,
RAM trim, automatic game detection) and a rule-based **Automation** engine.

> 💡 **Live demo without installing:** open [`netmon_preview.html`](netmon_preview.html) in any browser
> for an interactive mockup of the UI with simulated data.

---

## ✨ Features

| Tab | What it does |
|---|---|
| 🖥 **Dashboard** | Live DL/UL speed charts, total traffic, per-process network/CPU/RAM table, live connection list with risk hints, right-click kill / block via firewall |
| 📈 **History** | Trend charts (bandwidth, ping, CPU/RAM), daily HTML/PDF reports, ping history, and the last-7-days **connected hosts** you talked to |
| 📊 **Adapters** | Active network adapters (IP, MAC, speed, MTU, counters), primary adapter info, DNS servers, connection status |
| ⚡ **Speed Test** | Download / upload / ping / jitter measurement against public endpoints |
| 🌍 **Geo-IP** | Resolve and map IP addresses & domains (country, ISP, coordinates) |
| 📡 **Ping Monitor** | Live multi-host ping graph with packet-loss indicators |
| 🔌 **Port Scanner** | Fast port scanning with ranges & lists (`20-1024`, `80,443`, mixed) |
| 🧪 **DNS Tools** | DNS lookup, reverse lookup, system DNS inspection, cache flush |
| ⚙️ **Set DNS** | Switch system DNS servers (built-in presets incl. Iranian resolvers) |
| 📶 **IP Scanner** | Scan your LAN for live hosts |
| 🚀 **Game Boost** | Auto-detect 90+ known games, QoS-style per-app priority, live game-server IP + ping, Power Plan switching, RAM trim, I/O + CPU priority |
| 🎮 **Game Servers** | Built-in + custom game server endpoints with live ping |
| 🤖 **Automation** | IF-THEN rules (ping/CPU/bandwidth/time triggers) and one-click profiles — no JSON needed (structured editor, JSON fallback) |
| 🗂 **Config Dump** | Export full diagnostics (system, adapters, QoS, firewall, settings) |
| ❓ **Help** | Full Persian/English guide with live search + a 5-step first-run tutorial |

**Extra goodies:** system tray support (optional), firewall block/unblock per process, keyboard
shortcuts (`Ctrl+R` refresh, `Ctrl+E` export, `Ctrl+P` pause, `Ctrl+K` kill), theme switching,
responsive layout that adapts to any resolution, and auto-saved settings.

---

## 🚀 Getting Started

### Requirements

- **Python 3.10+** (developed on 3.13)
- A desktop environment with Tk support
- **Windows** for the full feature set (QoS / power plan / I/O priority / firewall). The app runs on
  Linux & macOS with a reduced feature set.

### Installation

```bash
# 1. Clone or download the repo, then create a virtual environment
python -m venv .venv

# 2. Activate it
#    Windows:
.venv\Scripts\activate
#    Linux / macOS:
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
```

Optional (adds a system-tray icon):

```bash
pip install pystray Pillow
```

### Usage

```bash
python network_monitor.py
```

> ⚠️ **Windows:** run **as Administrator** for full functionality — QoS policies, I/O priority,
> firewall rules and some connection tables require elevated privileges. Without admin rights the
> app still runs; those sections just show limited data.

**First run:** a short 5-step guided tour walks you through the most important tabs (Skip with the
button or `Esc`; replay it anytime from the Help tab).

---

## 📁 Files it creates next to the script

| File | Purpose |
|---|---|
| `netmon_settings.json` | UI / QoS / host preferences (atomic write) |
| `netmon_history.db` | SQLite trends + connected-host history (30-day prune) |
| `automation_rules.json` | Your automation rules & profiles |
| `custom_game_servers.json` | Custom game-server endpoints |
| `netmon.log` | Rotating log (5 MB × 3) |
| `netmon_report_<ts>.html` / `.pdf` | Daily reports from the History tab |

All of these are git-ignored and safe to delete — they are recreated on next start.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+R` | Refresh everything |
| `Ctrl+E` | Export report |
| `Ctrl+P` | Pause / resume monitoring |
| `Ctrl+K` | Kill selected process |

---

## 🏗 Project Layout

```
network_monitor.py   ← the entire app (single file, ~11k lines)
netmon_preview.html  ← interactive UI mockup for the browser (demo only)
requirements.txt     ← dependencies
```

---

## 🇮🇷 فارسی — خلاصه

یک مانیتور شبکهی پیشرفته و تمامعیار به زبان پایتون با رابط گرافیکی مدرن (CustomTkinter):

- **داشبورد زنده:** سرعت دانلود/آپلود، مصرف هر برنامه، لیست اتصالات، بستن و مسدودکردن برنامهها
- **تست سرعت، پینگ، اسکن پورت و IP، ابزارهای DNS و Geo-IP**
- **گزارش روزانه HTML/PDF** و تاریخچهی هفتگی هاستهای متصلشده
- **گیم بوست:** تشخیص خودکار ۹۰+ بازی، اولویتدهی به ترافیک بازی، نمایش IP و پینگ سرور بازی،
  تغییر پاورپلن، آزادسازی RAM و اولویت I/O
- **اتوماسیون:** قانونهای «اگر … آنگاه …» و پروفایلهای یککلیکی بدون نیاز به JSON
- **راهنمای کامل فارسی** با جستجو و تور آموزشی ۵ مرحلهای برای اولین اجرا

برای اجرا: `pip install -r requirements.txt` سپس `python network_monitor.py` (در ویندوز با
**Administrator** اجرا کنید تا همهی امکانات فعال شوند).

---

## 📄 License

[MIT](LICENSE)
