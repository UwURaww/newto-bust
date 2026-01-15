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

# Installations
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

# or
sudo bash netwo_burst.sh
```
# Quick install
```bash
proot-distro login archlinux -- bash -c "pacman -Syu --noconfirm && pacman -S git curl iputils bc --noconfirm && git clone https://github.com/UwURaww/netwo-bust.git && cd netwo-burst && chmod +x netwo_burst.sh && ./netwo_burst.sh"
```

