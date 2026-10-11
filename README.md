# Farcall releases

Farcall lets you chat with Claude Code sessions running on your Mac, Windows PC or Linux machine from your phone, privately: the phone reaches the computer over your own Tailscale network, not through a public server.

This repository only holds the builds. Download from **[Releases](https://github.com/eamon831/farcall-releases/releases/latest)**.

## Install

**Mac** (Apple Silicon, macOS 13 or later)

In Terminal:

```sh
curl -fsSL https://github.com/eamon831/farcall-releases/releases/latest/download/install.sh | bash
```

It downloads the newest Farcall, checks it against the release's checksum, installs it into Applications and opens it. [Read the script](https://github.com/eamon831/farcall-releases/releases/latest/download/install.sh) first if you like.

Then follow the setup in the Farcall window. It installs and signs in what is needed, one step at a time, and updates itself afterwards.

Or with the disk image: download `Farcall.dmg`, open it, drag Farcall to Applications, open it. The first time macOS says it cannot verify the app: click Done, then System Settings › Privacy & Security › **Open Anyway** (Farcall is not yet signed with an Apple Developer ID; the Terminal way avoids this).

**Windows** (64-bit Windows 10 or 11). New, not yet tried on many PCs.

In PowerShell:

```powershell
irm https://github.com/eamon831/farcall-releases/releases/latest/download/install.ps1 | iex
```

It downloads the newest Farcall, checks it against the release's checksum, installs it for your account only (no administrator needed) into `%LOCALAPPDATA%\Programs\Farcall`, adds it to the Start menu and opens it. [Read the script](https://github.com/eamon831/farcall-releases/releases/latest/download/install.ps1) first if you like. Then follow the setup in the Farcall window, as on the Mac.

**Linux** (x64, a desktop with GTK 3; systemd for the background service). New, not yet tried on many machines.

In a terminal:

```sh
curl -fsSL https://github.com/eamon831/farcall-releases/releases/latest/download/install-linux.sh | bash
```

It downloads the newest Farcall, checks it against the release's checksum, installs it for your account only (no sudo) into `~/.local/opt/farcall`, adds a menu entry and opens it. [Read the script](https://github.com/eamon831/farcall-releases/releases/latest/download/install-linux.sh) first if you like. Then follow the setup in the Farcall window.

**Phone** (Android)
1. Download `farcall.apk` on the phone (the Mac's setup shows a QR code for it) and install it.
2. In the app: Add a Mac, and scan the code from the Mac's "Pair phone".

## What is inside

Farcall includes Tailscale's open-source client (`tailscaled`, BSD-3-Clause, © Tailscale Inc & contributors) to connect your devices without the Tailscale app. Its license is in `Farcall.app/Contents/Resources/tailscale/LICENSE` (Windows and Linux: `tailscale/LICENSE` in the install folder).
