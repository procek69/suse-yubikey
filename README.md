# suse-yubikey

If you want to allow yubikey to work on suse, you will need to execute these commands:

```sh
sudo nano /etc/udev/rules.d/70-YubiKey.rules
```

Then paste this:
```txt
 # Yubico YubiKey
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{idVendor}=="1050", ATTRS{idProduct}=="0113|0114|0115|0116|0120|0200|0402|0403|0406|0407|0410", TAG+="uaccess", GROUP="plugdev", MODE="0660"
```

Reload rules:
```sh
sudo udevadm control --reload-rules
```

Based on https://forums.opensuse.org/showthread.php/534862-Google-Titan-security-key-for-logging-into-Gmail-Google-Account
