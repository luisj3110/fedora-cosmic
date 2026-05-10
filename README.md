# Fedora COSMIC Minimalist

### A clean, high-performance, Rust-powered installer for Fedora Everything

This script is designed for developers and creatives who want a rock-solid, bloat-free environment powered by the **COSMIC Desktop Environment**. It transforms a minimal Fedora base into a robust professional workstation, meticulously optimized for heavy data pipelines and AAA 3D production.

## The Philosophy

Most "out of the box" distros come with tools you'll never use. This project takes the opposite approach: **Start with nothing, add only what matters.**

* **Rust-Powered Efficiency:** Uses the `cosmic-comp` compositor for a modern, memory-safe, and highly performant workflow.
* **Performance First:** Aggressive DNF optimizations and a strict "No-Daemon" policy for Docker to keep startup RAM usage around **1GB**.
* **Creative-Ready:** Built-in support for **Huion/Wacom** tablets and 3D libraries (OpenGL/Vulkan) for professional-grade assets.
* **Data Engineering Focused:** A deterministic environment ready for SQL, Spark, and containerized pipelines without system-level friction.

## Key Features

### System Optimization

* **DNF Speedup:** Configures 10 parallel downloads and fastest mirror detection for lightning-fast updates.
* **Surgical Base:** Avoids meta-packages and "Weak Dependencies." You get the core COSMIC stack without the `cosmic-store` or unnecessary applets.
* **Modern Audio:** Full **PipeWire** stack with WirePlumber for low-latency audio processing.

### Graphics & Hardware

* **NVIDIA Setup:** Automates **RPM Fusion** repos and forces `akmods` compilation. To prevent the "black screen" lottery on the first reboot.
* **AMD Ryzen Optimization:** Includes `amd-ucode` and tailored power profiles**.
* **High-Refresh Ready:** Native Wayland support, ensuring a tear-free visual experience.

### Application Stack

A carefully curated list of tools focused on a "Vanilla Plus" aesthetic and production efficiency:

* **Browser:** **Brave** (Privacy-hardened and fast).
* **Terminal:** **Kitty** (GPU-accelerated) with a custom dotfile-ready configuration.
* **Monitoring:** `btop` for real-time resource tracking.

## How to Use

### 1. Pre-installation (Fedora Everything)

To keep the system as lean as possible, use the **Fedora Everything ISO** and select the following in the *Software Selection* step:

* **Base Environment:** Select `Fedora Custom Operating System`.
* **Add-ons:** `Standard`: For terminal decorators and bash-completion.
* `C Development Tools and Libraries`: **Mandatory** for NVIDIA driver compilation.
* `Common NetworkManager Submodules`: To ensure stable connectivity.
* `System Tools`: Access to `grubby` and disk management.



### 2. Execution

```bash
git clone https://github.com/luisj3110/fedora-cosmic.git
cd fedora-cosmic
chmod +x fedora_cosmic_install.sh
sudo ./fedora_cosmic_install.sh

```

## Safety & Logging

The script uses `set -euo pipefail` to ensure that if any critical step fails, the installer stops immediately to protect your system. Every action is logged to `install.log` for easy debugging.

## Tech Stack

* **OS:** Fedora Linux (Everything Edition).
* **DE:** COSMIC (Minimalist Rust-based Configuration).
* **Shell:** Bash / Kitty Terminal.
* **Drivers:** Proprietary NVIDIA + Wacom/Huion Support.

## License

MIT. Feel free to fork it, break it, and make it your own.
