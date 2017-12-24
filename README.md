systemlund
===

emlun's systemd units.


Usage
---

Arch Linux users:

    $ makepkg -i
    # systemctl daemon-reload
    # systemctl enable screenlock.target
    # systemctl enable screenlock@emlun.service
    # systemctl enable restart-openvpn-client@foo.service
