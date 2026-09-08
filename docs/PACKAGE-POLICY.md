# Package policy (v01 anti-bloat)

Admission test for every new entry in `profile/packages.x86_64`:

1. Needed to install / recover / connect? If not, reject.
2. One app per role (one terminal: konsole, one browser: firefox, one file manager: dolphin).
3. No meta-packages (`plasma-meta`, `kde-applications-meta`).
4. No Office, Discover, PIM, games in 01.
5. Prefer existing Arch `[core]/[extra]` package, no custom repo in 01.

Removal candidates for v01 (rescue parity dropped):
`clonezilla, partimage, partclone, fsarchiver, testdisk, ddrescue, cloud-init,
bind, ldns, dnsmasq, darkhttpd, lftp, irssi, lynx, nbd, open-iscsi, pptpclient,
vpnc, brltty, espeakup`.
