# Farcall

**One phone remote for the AI coding agents on your computer.** Claude Code (on Claude, GLM, Kimi or Gemini) and Codex (on OpenAI), side by side in one app, even in the same chat. When an agent asks "Can I run `npm test`?", tap Allow and it keeps going. End-to-end encrypted over your own Tailscale network, with no Farcall server in between.

**Works where Anthropic's Remote Control won't:** Claude Code on GLM, Kimi or OpenRouter (Remote Control accepts only Anthropic's own API), and nothing to keep open on your computer: Farcall runs as a background service.

*Using another coding CLI? [Tell us which one →](https://github.com/eamon831/farcall-releases/issues/1)*

<p align="center">
  <picture><source media="(prefers-color-scheme: dark)" srcset="images/shot-phone-chat-dark.png"><img src="images/shot-phone-chat-light.png" alt="A chat: the agent explains the bug, edits the file, and asks before running npm test (Allow / Deny)" width="260"></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="images/shot-phone-sessions-dark.png"><img src="images/shot-phone-sessions-light.png" alt="Sessions on a computer: one waiting for your approval, one working, one done" width="260"></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="images/shot-phone-new-session-dark.png"><img src="images/shot-phone-new-session-light.png" alt="New session: pick a project folder and an agent: Claude, Claude on GLM or Kimi, or Codex" width="260"></picture>
</p>

- **Your agent, your model.** Claude Code on your Claude login, or on Z.ai's GLM or Moonshot's Kimi; Gemini through OpenRouter (preview). Codex on your OpenAI login (preview). Pick per session.
- **You approve every command.** When the agent wants to run a command or edit a file, your phone asks first: Allow or Deny, from anywhere. You can see what it is doing while it works.
- **No server in the middle.** Your phone reaches your computer over your own private [Tailscale](https://tailscale.com) network, built into Farcall: no Tailscale app to install. Your chats and code stay on your machines.
- **Mac, Windows and Linux** on the computer, **Android** on the phone. iPhone: not yet.

## How is it different?

Remote apps for coding agents usually tie you to one agent, one account, or a company server that sits in your session. Farcall:

- **Works with any of your providers**, not one account: Claude, GLM, Kimi, Gemini (OpenRouter) and Codex, side by side.
- **Has no server of its own.** Phone and computer connect over your own Tailscale network, end-to-end encrypted. (When they cannot reach each other directly, Tailscale relays the encrypted traffic, which it cannot read.)
- **Asks before every command**, with the request on your phone, not just a notification after the fact.
- **Can put two or three agents in one chat** (a panel): they answer side by side and can discuss each other's answers.
- **Updates your computer from your phone:** Settings › Update Farcall on that computer.

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="images/diagram-wide-dark.svg"><img src="images/diagram-wide-light.svg" alt="How Farcall connects: phone, over your private Tailscale network, to Farcall on your computer, which runs your coding agent, which talks to your AI provider" width="800"></picture></p>

**Website: [farcall.app](https://farcall.app)** · This repository holds the builds only. **[Download the latest release](https://github.com/eamon831/farcall-releases/releases/latest)**

## What you need

- **A computer** that stays on while you use it: a Mac (Apple Silicon, macOS 13+), a Windows PC (64-bit Windows 10 or 11) or a Linux machine (x64, Ubuntu 22.04 or newer or a similar distribution, with a desktop and systemd).
- **An Android phone.**
- **One AI to work with**, any of: a Claude account (setup signs you in), a Z.ai (GLM), Moonshot (Kimi) or OpenRouter (Gemini, preview) API key, or Codex signed in to your OpenAI account. One is enough; setup installs Claude Code when the one you pick needs it.
- **A Tailscale account**, free for personal use. You sign in from inside Farcall on both devices; the Tailscale app itself is not needed.

## Getting started

**1. Install Farcall on the computer.** Pick your system below. Each installer downloads the newest build, checks it against the release's checksum, installs it for your account only and opens it.

<details open>
<summary><b>Mac</b></summary>

In Terminal:

```sh
curl -fsSL https://github.com/eamon831/farcall-releases/releases/latest/download/install.sh | bash
```

Prefer a disk image? Download `Farcall.dmg` from the release, drag Farcall to Applications and open it. The first time, macOS says it can't verify the app (Farcall isn't signed with an Apple Developer ID yet): click Done, then System Settings › Privacy & Security › **Open Anyway**. The Terminal way skips this.
</details>

<details>
<summary><b>Windows</b> (new)</summary>

In PowerShell (no administrator needed):

```powershell
irm https://github.com/eamon831/farcall-releases/releases/latest/download/install.ps1 | iex
```

Installs into `%LOCALAPPDATA%\Programs\Farcall` and adds Farcall to the Start menu.
</details>

<details>
<summary><b>Linux</b> (new)</summary>

In a terminal (no sudo):

```sh
curl -fsSL https://github.com/eamon831/farcall-releases/releases/latest/download/install-linux.sh | bash
```

Installs into `~/.local/opt/farcall` and adds a menu entry.
</details>

You can read each script before running it: [install.sh](https://github.com/eamon831/farcall-releases/releases/latest/download/install.sh), [install.ps1](https://github.com/eamon831/farcall-releases/releases/latest/download/install.ps1), [install-linux.sh](https://github.com/eamon831/farcall-releases/releases/latest/download/install-linux.sh).

**2. Follow the setup in the Farcall window.** Four steps, each checked for you: **Connect** (sign in to Tailscale), **Pick your AI** (sign in, or paste a key), **Projects folder**, **Pair your phone**. Farcall installs Claude Code and checks that approvals reach your phone by itself.

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="images/shot-desktop-setup-dark.png"><img src="images/shot-desktop-setup-light.png" alt="The setup window: Pick your AI, with Claude signed in and a GLM key stored" width="640"></picture></p>

**3. Install the phone app.** The setup's phone step shows a QR code; scan it with the phone's camera, or download `farcall.apk` from the release. Allow installing from your browser when Android asks.

**4. Connect and pair.** Open Farcall on the phone. Under **Connect this phone**, tap **Sign in** and use the same Tailscale account as the computer. Then tap **Pair phone** in the computer's window and scan its code with **Scan the code** on the phone.

That's it. On the phone, tap **Start a new session**, pick a project folder, and chat.

## Keep the computer awake

Farcall runs on your computer, so it only works while that computer is awake. A sleeping computer shows as offline on the phone, and a reply the agent was writing stops until it wakes. Farcall can't wake it from the phone.

Turn off automatic sleep while it's plugged in:

- **Mac desktop** (Mac mini, iMac, Mac Studio): System Settings › Energy › turn on **Prevent automatic sleeping when the display is off**.
- **MacBook:** System Settings › Battery › Options › turn on **Prevent automatic sleeping on power adapter when the display is off**. Keep it plugged in. Closing the lid still puts it to sleep, unless an external display is connected.
- **Windows:** Settings › System › Power (Power & battery on Windows 11) › set sleep **when plugged in** to **Never**.
- **Linux** (Ubuntu): Settings › Power › turn off **Automatic Suspend** (at least when plugged in).

The screen can still turn off. Only the computer has to stay awake.

## Privacy and security

- **No middleman.** The phone reaches the computer directly over your Tailscale network. Farcall runs no server and never sees your chats, code or files.
- **Paired devices only.** The computer listens only on its Tailscale address and accepts only phones that scanned its pairing code.
- **You approve each command.** By default the agent asks before it runs a command or edits a file, and the request comes to your phone. You can choose looser modes per session.
- **Who makes it.** Made by MD Saiful Hossain ([@eamon831](https://github.com/eamon831)), who built Farcall to run his own Claude Code sessions from his phone. The source isn't public yet. Every build here is published with its SHA-256, and each installer checks it before installing, for your account only.
- **Crash reports** are on by default and can be turned off any time (phone: Settings › Privacy; computer: **Check setup** in the Farcall window). They contain only the error and where in Farcall it happened, with folder names, network addresses and keys removed: never your chats or files. They go to [Sentry](https://sentry.io).

## Updating and uninstalling

Farcall checks for updates itself: **Check for update** in the computer window and in the phone's Settings. Updates install in place and keep your sessions and pairing.

To remove it from a computer, use **Uninstall…** in the Farcall window. It stops the background service and removes the app, and with it Farcall's data and pairing (untick the box to keep those). Your Claude Code install and conversations are left alone. On the phone, uninstall the app as usual.

## When something doesn't work

- **The phone can't reach the computer:** check that the computer is awake (see [Keep the computer awake](#keep-the-computer-awake)), that its Farcall setup shows Tailscale ✓, and that the phone is signed in to the **same** Tailscale account (phone: Settings › Connection).
- **The first connection after an update takes a few seconds:** the built-in Tailscale is starting up. It settles by itself.
- **macOS won't open the app:** see the Mac section above (Open Anyway), or install from Terminal.

## Feedback

[Report a problem or suggest a feature](https://github.com/eamon831/farcall-releases/issues/new/choose). In the app, **Report a problem / Suggest a feature** opens the same form with your versions filled in. A GitHub account is needed, and reports are public, so look through any log lines before pasting them.

## Third-party software

Farcall includes Tailscale's open-source client (`tailscaled`, BSD-3-Clause, © Tailscale Inc & contributors) so your devices can connect without the Tailscale app. Its license is in `Farcall.app/Contents/Resources/tailscale/LICENSE` on a Mac, and in `tailscale/LICENSE` inside the install folder on Windows and Linux.
