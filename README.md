# Bekaros 01

Minimal Arch-based live ISO with KDE Plasma + SDDM and archinstall.

Live user: `bekar` (autologin on SDDM, passwordless sudo for install).
Browser: Firefox. No Kate. No custom repo in 01 — stock `[core]` + `[extra]` only.

## Build

```bash
sudo pacman -S --needed archiso
sudo mkarchiso -v -w /tmp/bekaros-work -o out profile/
ls -lh out/
```

## Test boot (QEMU)

```bash
qemu-system-x86_64 -enable-kvm -m 4G -cdrom out/*.iso -boot d
# UEFI:
qemu-system-x86_64 -enable-kvm -m 4G -drive if=pflash,format=raw,readonly=on,file=/usr/share/ovmf/x64/OVMF_CODE.fd -cdrom out/*.iso
```

Expected: SDDM autologin as `bekar` → Plasma → run `archinstall` to install.

## Package policy

See `docs/PACKAGE-POLICY.md`. Rule: one app per role, no `plasma-meta`, no Office/Discover/PIM in 01.

## Branding

Assets not final. Placeholders tracked in `profile/branding/TODO-ASSETS.md`.

## License

GPL-3.0-or-later. See `LICENSE`.
This profile derives from archiso `releng` (GPL-3.0-or-later).
