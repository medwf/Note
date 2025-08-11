## 1 Check which sensor you really have
1.  to install `lsusb` : `sudo pacman -S usbutils`.
```bash
lsusb | grep -i finger
```

Typical XPS 17 9700 output is:

```
Bus 003 Device 002: ID 27c6:533c Shenzhen Goodix Technology Co.,Ltd. FingerPrint
```

- `27c6:533c` → choose the **xps9300** Goodix driver
- `27c6:550a` or other Goodix IDs → choose the **goodix** driver

(The machine ships only Goodix sensors, so if you see something else stop here and tell me.) ([Linux Hardware](https://linux-hardware.org/?id=usb%3A27c6-533c&utm_source=chatgpt.com "Shenzhen Goodix Technology FingerPrint - Linux Hardware Database"))

---

## 2 Install the core fprint stack

```bash
sudo pacman -Syu fprintd base-devel git
```

---

## 3 Pull in the proprietary Goodix TOD driver from the AUR

### If your ID is **27c6:533c / 53 xc**

```bash
git clone https://aur.archlinux.org/libfprint-2-tod1-xps9300-bin.git
cd libfprint-2-tod1-xps9300-bin
makepkg -si
```

This package bundles the Dell-supplied Goodix blob and the “TOD” (Touch OEM Driver) wrapper. ([AUR](https://aur.archlinux.org/packages/libfprint-2-tod1-xps9300-bin?utm_source=chatgpt.com "libfprint-2-tod1-xps9300-bin - AUR (en) - Arch Linux"))

### If your ID is **27c6:550a** (or the 550x Lenovo variant)

```bash
git clone https://aur.archlinux.org/libfprint-2-tod1-goodix.git
cd libfprint-2-tod1-goodix
makepkg -si
```

([AUR](https://aur.archlinux.org/packages/libfprint-2-tod1-goodix?utm_source=chatgpt.com "AUR (en) - libfprint-2-tod1-goodix - Arch Linux"))

_Only one_ of these packages can coexist with the stock `libfprint`, so let pacman remove/replace the normal library if it asks. ([Manjaro Linux Forum](https://forum.manjaro.org/t/goodix-fingerprint-sensor-53xc-finally-working-again/110690?utm_source=chatgpt.com "Goodix Fingerprint Sensor 53xc : finally working again"))

---

## 4 Start & enable the daemon

```bash
sudo systemctl enable --now fprintd.service
```

Check that it detected the sensor:

```bash
systemctl status fprintd
```

You should see a line similar to  
`Creating TOD wrapper for goodix-tod (Goodix Fingerprint Sensor 53xc)` ([AUR](https://aur.archlinux.org/packages/libfprint-2-tod1-xps9300-bin?utm_source=chatgpt.com "libfprint-2-tod1-xps9300-bin - AUR (en) - Arch Linux"))

---

## 5 Enroll a finger

With the daemon running, as **your normal user** do:

```bash
fprintd-enroll
```

Follow the prompts; a complete pass normally takes 5-7 swipes/taps.

You can verify with:

```bash
fprintd-verify
```

---

## 6 Hook PAM so Hyprland-based logins & sudo recognise the print

### 6.1 System TTY, sudo, polkit …

Add the module _before_ the normal Unix line in the relevant PAM files, e.g.:
- hadi 3adi fiha mochkil
```bash
# /etc/pam.d/system-local-login
auth      sufficient   pam_fprintd.so
```

- hadi dyal sudo li khadama.
```bash
# /etc/pam.d/sudo
auth      sufficient   pam_fprintd.so
auth      include      system-auth
```

(Feel free to copy the pattern anywhere you want fingerprint support.) ([Framework Community](https://community.frame.work/t/guide-solved-sudo-and-login-with-fingerprint-reader-under-kde-arch-linux/37009?utm_source=chatgpt.com "[GUIDE/SOLVED] Sudo and Login with Fingerprint Reader under ..."))

### 6.2 greetd / Hyprland sessions
- hadi dyal hyprland ma3adakch nta.
HyDE’s preset usually logs in through **greetd**. Edit `/etc/pam.d/greetd` (or the greeter file you actually use) the same way:

```bash
auth      sufficient   pam_fprintd.so
```

greetd, hyprlock and swaylock all respect PAM, so after this change fingerprint unlock works for:

- the TTY login opened by greetd
- hyprlock / swaylock screen lockers
- sudo / pkexec prompts inside Hyprland

There is no extra Hyprland-specific code to write. If you need an example, see the hyprlock PAM snippet discussed here. ([GitHub](https://github.com/hyprwm/hyprlock/issues/4?utm_source=chatgpt.com "Pam entry · Issue #4 · hyprwm/hyprlock - GitHub"))

---

## 7 Test end-to-end

1. **Log out** and at the greetd prompt just tap the reader—your user should log in without typing a password.
    
2. Inside the session run `sudo echo test`; press **Enter** once, then touch the sensor.
    
3. `hyprlock` or `swaylock` → hit **Enter** and touch again.
    

If any step hangs, run `journalctl -u fprintd -b` and look for obvious errors.

---

## 8 Troubleshooting notes

- **Daemon does not see the device** → confirm you installed the correct `libfprint-2-tod1-*` flavour for your USB ID.
- **Works until suspend, then crashes** → upgrade BIOS to at least 2.4 on the 9700 and update to the latest driver blob; older Goodix firmware had a resume bug. ([Arch Linux Forums](https://bbs.archlinux.org/viewtopic.php?id=269743&utm_source=chatgpt.com "Dell XPS 17 9710 (i7-11800H) stuck in extremely power limited state"))
- **Multiple prints / finger errors** → just rerun `fprintd-enroll` and overwrite.
- **Want password _or_ print, whichever is quicker?** Keep `pam_fprintd.so` flagged **sufficient** (not **required**) as shown above.    
