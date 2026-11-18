# s32

Command-line editor for the Shik S32 MIDI controller.

Download installable archives from **[Releases](https://github.com/Shik-Tech/S32-CLI/releases)**.
Handbook: https://s32-manual.shik.tech/developers/

## Install

One line, no download page, no `sudo` for the CLI itself.

macOS and Linux:

```sh
curl --proto '=https' --tlsv1.2 -fsSL https://github.com/Shik-Tech/S32-CLI/releases/latest/download/install.sh | sh
```

Windows (PowerShell):

```powershell
irm https://github.com/Shik-Tech/S32-CLI/releases/latest/download/install.ps1 | iex
```

The script installs `s32` into `~/.local/bin` (macOS, Linux) or `%LOCALAPPDATA%\Programs\s32` (Windows), checks the download against `SHA256SUMS` from the same release, and tells you if the folder is not on your `PATH`. To pin a version, set `S32_VERSION=1.3.45` (Windows: `$env:S32_VERSION='1.3.45'`) or pass `sh -s -- --version 1.3.45`.

Each script is also a release asset, with its SHA-256 listed in `SHA256SUMS`. Read it before you run it if you prefer.

On Linux the script asks before it installs the USB rule (it runs `sudo`) and needs `libusb-1.0` from your distribution (Debian / Ubuntu: `sudo apt-get install libusb-1.0-0`; Fedora: `sudo dnf install libusb1`). macOS and Windows need nothing else.

### Manual install

Pick the archive for your machine (`darwin-arm64`, `darwin-x64`, `linux-x64`, or `windows-x64`) from **Releases**. Each archive contains the `s32` binary (or `s32.exe` with its DLLs) and a short `INSTALL.txt`. On Linux, install `99-s32-editor.rules` from the tarball so `--usb` works without root (VID `0483`, PID `a56e`).

```bash
s32 --version
s32 --loopback hello   # no hardware
s32 --usb hello        # attached S32
```

## USB

s32 talks to the **S32 Editor** USB interface — the same connection the web editor uses. It is not USB MIDI.

Connecting over USB claims that interface exclusively and is full device control. Close any web editor tab first. Destructive commands ask for confirmation unless you pass `--yes`.

## Docs

Command reference and examples: https://s32-manual.shik.tech/developers/
