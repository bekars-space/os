# Build

Requires Arch Linux + `archiso`.

```bash
sudo pacman -S --needed archiso git
git clone git@github.com:bekars-space/os.git
cd os
sudo mkarchiso -v -w /tmp/bekaros-work -o out profile/
```

Outputs: `out/bekaros-01-*.iso` + `SHA256SUMS` (CI generates sums).

Clean rebuild:

```bash
sudo rm -rf /tmp/bekaros-work out
sudo mkarchiso -v -w /tmp/bekaros-work -o out profile/
```

CI (`build.yml`) does the same in a privileged `archlinux/archlinux:latest`
container on `master` / `v*` tags / manual dispatch.
