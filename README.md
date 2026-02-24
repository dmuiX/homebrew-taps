# homebrew-taps 🍺

[![Homebrew](https://img.shields.io/badge/Homebrew-Tap-FBB040?logo=homebrew&logoColor=white)](https://brew.sh/)
[![Platform](https://img.shields.io/badge/platform-macOS-lightgrey)](#)
[![Type](https://img.shields.io/badge/packages-casks-blue)](#available-casks-)

Custom Homebrew tap for macOS packages that are niche, deprecated, or not maintained in official Homebrew repositories.

## Quick Start 🚀

```bash
brew tap dmuiX/taps
brew install --cask tuxguitar
```

## Available Casks 📦

| Cask | Description | Install |
| --- | --- | --- |
| `tuxguitar` 🎸 | Multitrack guitar tablature editor and player | `brew install --cask tuxguitar` |

## Why This Tap Exists 🤔

- 🧰 Maintain deprecated or niche macOS applications
- ♻️ Keep reproducible installations across machines
- 🛡️ Reduce dependency on Homebrew core cask policy constraints

## Troubleshooting 🛠️

### Gatekeeper / Quarantine 🔐

Some apps in this tap may not be notarized by Apple. If macOS blocks an app, remove the quarantine attribute:

```bash
xattr -dr com.apple.quarantine /Applications/<AppName>.app
```

## Disclaimer ⚠️

Personal-use tap. Use at your own discretion.

## AI Notice 🤖

This repository contains AI Code and AI-assisted documentation updates.
