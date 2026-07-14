# ⚡ Optima - Hardcore eSports Dashboard

![Version](https://img.shields.io/badge/version-0.2.0-red.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![Language](https://img.shields.io/badge/language-Rust-orange.svg)

**Optima** is an ultra-lightweight, zero-impact system monitoring and kernel-level optimization HUD. Designed explicitly for competitive eSports environments (like Counter-Strike 2 and Valorant), it ensures absolute minimum input latency, maximum hardware utilization, and stable frametimes—all wrapped in a sleek, transparent Glass UI.

## 🚀 Features

### 🛡️ Smart Adaptive Core Isolation
Optima dynamically reads your CPU topology (fully supporting both AMD Ryzen and Intel architectures). It executes a pyramid-based thread assignment algorithm:
* **Core 0** is strictly isolated for the Windows Kernel and USB Interrupts (Mouse/Keyboard) to guarantee 1:1 raw input with zero latency spikes.
* **Background Apps** (Discord, Spotify, etc.) are restricted to secondary cores.
* **100% of the remaining computational power** is locked exclusively to your target game process.

### 💨 Kernel & Network Optimization
* **Timer Resolution Override:** Forces the system timer from the default 15.6ms down to a synchronized **1.0ms - 2.0ms** for instantaneous frame pacing.
* **TCP NoDelay & Packet Loss Mitigation:** Injects raw networking rules to bypass default Windows throttling and activate QoS/ECN for minimum ping.
* **Smart Memory Purge:** Monitors background RAM usage and silently flushes empty working sets either manually or automatically every 10 minutes.

### 👁️ Zero-Impact Glass HUD
Built using `egui`, the dashboard features a customizable opacity slider. It can be pinned over your background applications without obstructing your view. Using **Asynchronous Multi-Timer Polling**, Optima fetches system data without blocking the UI thread, ensuring the monitoring tool itself never causes the "Observer Effect" (lag).

### 🔄 Seamless Auto-Updater
No need to manually redownload patches. Optima runs a background thread that connects to GitHub APIs, checks for new releases, streams the update, safely swaps the binary, and restarts itself automatically.

---

## 📥 Installation

1. Navigate to the [Releases](../../releases) page.
2. Download the latest `optima-windows.zip` file.
3. Extract the `optima.exe` file anywhere on your system.
4. Run the executable as Administrator (Admin rights are highly recommended for applying priority and kernel-level tweaks).

