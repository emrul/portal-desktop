# Portal Desktop — release artifacts

This repository hosts **release artifacts only** (notarized macOS builds) as
GitHub Releases. The source code lives elsewhere.

Portal Desktop streams a Mac you own to a browser — real desktop pixels, hardware
H.264, dual-stream **4:4:4** colour for crisp text, **system audio**, and full
keyboard/mouse input, over **WebTransport** (same network) or **WebRTC**
(remote-capable). One shared Apple VideoToolbox encode feeds every connected client.

## Install (macOS, Apple Silicon · Sonoma 14+)

```sh
brew install --cask emrul/portal/portal-desktop
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
4. **Sign in** when the browser connects: enter this Mac's login password (it's
   checked against the OS account and remembered for ~12h per browser). The
   connection is over a self-signed certificate — verify its fingerprint against
   the menu-bar **Certificate Fingerprint…** item if you want to be sure there's
   no interception.
5. **Click the video** to take control — keyboard, mouse, and two-finger scroll
   forward to the Mac. Click outside the video to release. Toggle **🔊 audio** in
   the viewer's top bar (on by default).

## Updating

Portal Desktop is a Homebrew cask, so updating is one command:

```sh
brew update && brew upgrade --cask emrul/portal/portal-desktop
```

`brew update` refreshes the tap so Homebrew sees the newest release; `brew upgrade`
then downloads and installs it. Notes:

- **Quit the app first.** Click the menu-bar icon → **Quit** before upgrading, so
  Homebrew can replace the running bundle; relaunch from Spotlight afterwards.
- **Your permissions carry over.** Every build is signed with the same Developer
  ID, so the Screen Recording and Accessibility grants persist — no re-approval
  after an upgrade.
- **Check versions** (installed vs. latest available):
  ```sh
  brew info --cask emrul/portal/portal-desktop
  ```
- **Force a clean reinstall** if an upgrade ever looks off:
  ```sh
  brew reinstall --cask emrul/portal/portal-desktop
  ```
- **Uninstall:** `brew uninstall --cask emrul/portal/portal-desktop`.

## Releases

- **`app-v*`** — the notarized menu-bar app (`.dmg`), installed by the cask above.
  There is always exactly one current `app-v*` release; `brew upgrade` tracks it.
