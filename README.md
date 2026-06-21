# Portal Desktop — release artifacts

This repository hosts **release artifacts only** (notarized macOS builds) as
GitHub Releases. The source code lives elsewhere.

Portal Desktop streams a Mac you own to a browser — real desktop pixels, hardware
H.264, dual-stream **4:4:4** colour for crisp text, and full keyboard/mouse input,
over **WebTransport** (same network) or **WebRTC** (remote-capable). One shared
Apple VideoToolbox encode feeds every connected client.

## Install (macOS, Apple Silicon · Sonoma 14+)

```sh
brew install --cask emrul/portal/portal
```

This installs the notarized **Portal Desktop.app** — a menu-bar app with no other
dependencies. It encodes via Apple VideoToolbox, so **no ffmpeg** is required.

## Using it

1. Launch **Portal Desktop** from Spotlight or Applications. It lives in the menu
   bar (top-right) — there's no Dock icon.
2. On first launch, grant **Screen Recording** when prompted (System Settings →
   Privacy & Security). For keyboard/mouse control of this Mac, also grant
   **Accessibility**. Because the app is signed, these grants persist across
   upgrades.
3. From the menu-bar icon, **open the viewer** (or copy the link) and open it in
   **Chrome or Edge**. On the same machine use `https://127.0.0.1:8080` —
   "localhost" breaks WebTransport. For a remote browser, use the WebRTC viewer
   at `…/webrtc.html`.
4. **Click the video** to take control — keyboard, mouse, and two-finger scroll
   forward to the Mac. Click outside the video to release.

Upgrade with `brew upgrade --cask emrul/portal/portal`.

## Releases

- **`app-v*`** — the notarized menu-bar app (`.dmg`), installed by the cask above.
