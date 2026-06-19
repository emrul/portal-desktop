# Portal Desktop — release artifacts

This repository hosts **release artifacts only** (notarized macOS builds of
`portal-desktop`) as GitHub Releases. The source code lives elsewhere.

## Install (macOS, Apple Silicon)

```sh
brew install --cask emrul/portal/portal-desktop
```

This pulls the notarized binary from the Releases here and installs `portal-desktop`
onto your `PATH` (ffmpeg is installed automatically as a dependency).

First run prompts for **Screen Recording** (capture) and, with `--enable-input`,
**Accessibility** (keyboard/mouse) in System Settings → Privacy & Security.

```sh
portal-desktop --capture --enable-input
```

Then open the printed `https://…` URL in Chrome or Edge.
