# s32

Command-line editor for the Shik S32 MIDI controller.

Download installable archives from **[Releases](https://github.com/Shik-Tech/S32-CLI/releases)**.
Handbook: https://s32-manual.shik.tech/developers/

## Install

Pick the archive for your machine (`darwin-arm64`, `darwin-x64`, `linux-x64`, or `windows-x64`). Each archive contains the `s32` binary (or `s32.exe`) and a short `INSTALL.txt`.

Runtime dependency: **libusb-1.0**.

- macOS: `brew install libusb` (native Homebrew on Apple Silicon: `/opt/homebrew`)
- Debian / Ubuntu: `sudo apt-get install libusb-1.0-0`
- Fedora: `sudo dnf install libusb1`
- Windows: libusb-1.0 on `PATH`

Linux: install `99-s32-editor.rules` from the tarball so `--usb` works without root (VID `0483`, PID `a56e`).

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
