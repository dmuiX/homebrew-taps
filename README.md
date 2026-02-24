# homebrew-taps 🍺

Personal Homebrew tap containing custom casks and formulas that are not available (or no longer maintained) in the official Homebrew repositories.

## Installation ⚙️

Add this tap:

``` bash
brew tap dmuiX/taps
```

## Available Casks 📦

### TuxGuitar 🎸

Multitrack guitar tablature editor and player.

Install with:

``` bash
brew install --cask tuxguitar
```

## Why This Tap Exists 🤔

This repository is used to:

-   🧰 Maintain deprecated or niche macOS applications
-   ♻️ Keep reproducible installations across machines
-   🛡️ Avoid dependency on Homebrew core cask policies (e.g. Gatekeeper
    notarization enforcement)

## Gatekeeper Note 🔐

Some apps in this tap may not be notarized by Apple.\
If macOS blocks an app, you can remove the quarantine attribute:

``` bash
xattr -dr com.apple.quarantine /Applications/<AppName>.app
```

## Disclaimer ⚠️

This is a personal-use tap.\
Use at your own discretion.
