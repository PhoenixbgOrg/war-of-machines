<p align="center">
  <img src="docs/assets/promo/war-of-machines-readme-banner-900.png" width="900" alt="War of Machines — multiple AI models, one task, shared reasoning">
</p>

<p align="center"><b>PRIVACY IS A PRINCIPLE, NOT AN OPTIONAL FEATURE.</b></p>

<p align="center">War of Machines does not collect telemetry, user conversations, API keys, or usage history for RitualForge Labs. Application data is stored locally. When cloud AI models are used, selected requests are sent directly to the respective provider.</p>

<p align="center"><code>No telemetry · No tracking · Local-first · Your API keys · Your data</code><br><a href="PRIVACY_EN.md">Privacy policy (EN)</a> · <a href="PRIVACY_BG.md">Политика за поверителност (BG)</a></p>

<p align="center"><b>English</b> · <a href="README_BG.md">Български</a></p>

# War of Machines

A free desktop application in which several AI models from different providers work on **one task as a team** — they propose, criticise and revise each other's answers in one shared discussion.

## Contents
- [What it is and why it was created](#what-it-is-and-why-it-was-created)
- [How it works](#how-it-works)
- [Agreement is not proof](#agreement-is-not-proof)
- [Free, your keys, your costs](#free-your-keys-your-costs)
- [Languages](#languages)
- [Providers and models](#providers-and-models)
- [Modes](#modes)
- [Verification status](#verification-status)
- [Download and install](#download-and-install)
- [Screenshots](#screenshots)
- [Feedback](#feedback)
- [Licensing](#licensing)

## What it is and why it was created

Asking one AI model gives you one point of view, including its blind spots. War of Machines was created to let several real models — for example from OpenAI, Anthropic and Google — look at the same question together, point out each other's mistakes and improve the result, while you watch every step.

## How it works

1. You write a task and choose which models take part.
2. **Proposal** — the models give their first answers.
3. **Critique** — each model reviews the others' answers and points out errors, gaps and weak arguments.
4. **Revision** — the models revise their answers using the critique.
5. You see the whole discussion and the final answers, and decide yourself.

All participants are real AI models called through their providers' official APIs with your own keys. The discussion is saved locally on your computer.

## Agreement is not proof

When several models agree, that is **not proof that the answer is factually correct**. Models can share the same wrong information or reinforce each other. Treat the result as a well-argued draft and verify important facts from reliable sources.

## Free, your keys, your costs

- The application is **free**, with **no ads**. Support for the project is **voluntary**.
- You use **your own API keys**. Any fees are charged **by your provider** to your account; War of Machines does not charge anything and does not see your billing.
- **No automatic paid requests:** model lists and conversations are requested only when you start them.
- API keys are stored in your **system keyring** (for example GNOME Keyring), not in plain-text files. There is no telemetry.

## Languages

- User interface in **English** and **Bulgarian**.
- A separate setting for the **language of the AI discussion**, so you can, for example, use a Bulgarian interface while the models discuss in English.

## Providers and models

Supported providers: **OpenAI**, **xAI**, **Anthropic**, **Google Gemini**, **Mistral**, **DeepSeek**, **OpenRouter**, and optionally **local Ollama** (runs on your machine, no key needed).

The **model catalog is dynamic**: available models are loaded from each provider when you ask, so new models appear without an application update.

## Modes

| Mode | Status |
|---|---|
| **Mode A — AI Team** (proposal → critique → revision) | ✅ Available |
| **Mode B — Consensus Engine v0.4** | ⏳ **Not implemented** — a planned idea only |

The application also contains a **SIMULATION** provider for trying the interface without keys. **The simulator is not real AI**: it produces placeholder text and its results are never presented as a consensus.

## Verification status

| Area | Status |
|---|---|
| Automated tests | 119 passed / 1 skipped on the v0.1.1-beta release candidate (117 / 1 on the development baseline); offline, with fake local servers |
| Paid multi-model conversations with real cloud models | ✅ Manually verified by the owner (reported 2026-11-02, not automated) |
| Anthropic, Google Gemini, Mistral with real keys | ✅ Manually verified by the owner (reported 2026-11-02, not automated) |
| OpenAI model list with a real key | ✅ Verified by the owner (2026-10-30) |
| xAI model list with a real key | ✅ Verified by the owner (HTTP 403 until the account was funded) |
| GNOME Keyring storage | ✅ Verified by the owner |
| DeepSeek, OpenRouter with real keys | ❌ Not verified (tested only against a local fake server) |
| Windows, other Linux distributions | ❌ Not verified |

Tested on Debian 13 XFCE.

## Download and install

> **v0.1.1-beta (pre-release)** is available under [Releases](../../releases/tag/v0.1.1-beta). Download `war-of-machines-0.1.1-beta-linux-x86_64.tar.gz` and `SHA256SUMS`.

v0.1.1-beta is a **standalone compiled program for Linux x86_64**.
- It needs no Python and downloads nothing during installation.
- It installs per user, with no root.
- It is built for **Debian 13 (XFCE)**.
- **Not tested, feedback from testers expected:** other distributions, Wayland and HiDPI.

**Prerequisites (Debian 13).** These system libraries are usually already installed. `install.sh` checks for them and tells you if any are missing:

```bash
sudo apt install libxcb-cursor0 libxkbcommon-x11-0 libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-randr0 \
     libxcb-render-util0 libxcb-shape0 libxcb-xkb1 libxcb-xfixes0 libx11-xcb1 libegl1 libgl1 libdbus-1-3 libfontconfig1 libglib2.0-0t64
```

A Secret Service keyring (for example `gnome-keyring` or KeePassXC) is needed to save API keys.

```bash
sha256sum -c SHA256SUMS
tar xzf war-of-machines-0.1.1-beta-linux-x86_64.tar.gz
cd war-of-machines-0.1.1-beta-linux-x86_64
./install.sh
war-of-machines
```

- **Where it installs.** `install.sh` installs into `~/.local/share/war-of-machines` and adds a menu entry. It moves an older install aside and never deletes your data.
- **Uninstall.** `./uninstall.sh` removes the program and keeps your data.
- **Source code archives.** The "Source code" archives that GitHub adds automatically to every release contain only this project page, not the application.

## Screenshots

All screenshots use **synthetic demo data** and fake keys.

| | |
|---|---|
| ![Main window in English with demo conversation](docs/screenshots/main-en.png) | ![Main window in Bulgarian with demo conversation](docs/screenshots/main-bg.png) |
| Main window (EN) | Main window (BG) |
| ![Provider settings in English with fake demo keys](docs/screenshots/providers-en.png) | ![About dialog in English showing version 0.1.1-beta](docs/screenshots/about-en.png) |
| Providers (EN) | About (EN) |
| ![Mode A result produced by the simulator, marked as not real AI](docs/screenshots/mode-a-simulator-result-en.png) | |
| Mode A result with the simulator (not real AI) | |

## Feedback

Feedback is voluntary. Report bugs or ideas in [GitHub Issues](../../issues) or by email to info@ritualforgelabs.com. Please **do not include API keys, passwords or private conversations**. The application sends nothing automatically. If you attach a log, the application already hides keys and home-directory paths in it, but please check it yourself first. GitHub and your email provider process what you send under their own terms.

## Licensing

War of Machines is **freeware** under the [War of Machines Freeware License v1.0](LICENSE) (Bulgarian and English text; the Bulgarian text prevails). The licence applies to the released program packages. This repository contains only the project page; the application source code is not published. See also [LICENSING.md](LICENSING.md), [PRIVACY_EN.md](PRIVACY_EN.md), [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and the [name and image notice](docs/assets/promo/NOTICE.md).


Security issues: see [SECURITY.md](SECURITY.md). Changes: [CHANGELOG.md](CHANGELOG.md).

---

<p align="center">
Created by <b>Alexander Hristov</b> · Developed under <b>RitualForge Labs</b><br>
<a href="https://ritualforgelabs.com">ritualforgelabs.com</a> · <a href="https://phoenixcoreos.org">phoenixcoreos.org</a> · <a href="mailto:info@ritualforgelabs.com">info@ritualforgelabs.com</a>
</p>

<p align="center">
War of Machines is free and will stay without ads. If it is useful to you, you can support its development voluntarily via PayPal.Me: <a href="https://paypal.me/Hristov375">paypal.me/Hristov375</a>. The <i>Support via PayPal</i> button in the application's About window opens the same page in your browser. Support is never required and does not unlock features.
</p>

<p align="center">© 2026 Alexander Hristov / RitualForge Labs</p>
