# Arch Linux Installation – VMware Workstation

## System Summary
- **Boot:** UEFI with systemd-boot  
- **Desktop Environment:** XFCE + LightDM  
- **User:** Jake (sudo)  
- **Shell:** Zsh with color + aliases  
- **SSH:** Enabled  
- **Aliases:** `ll`, `update`, `install`, `cls`

---

## Steps Completed
1. Partitioned disk using `parted` (UEFI + GPT)
2. Installed base system (`pacstrap`)
3. Configured locale, time, hostname
4. Installed `systemd-boot`
5. Added sudo user *Jake*
6. Installed XFCE + LightDM
7. Installed and configured Zsh
8. Enabled SSH
9. Verified everything with `neofetch`, `lsb_release -a`, `hostnamectl`

---

## Problems & Fixes
| Problem | Fix |
|----------|-----|
| **fdisk: value out of range** | Used `parted` to create GPT partitions |
| **bootctl: Not booted with EFI** | Ignored inside chroot; verified UEFI on reboot |
| **LightDM inactive (dead)** | Installed `lightdm-gtk-greeter` and started service |
| **Password not accepted** | Reset via `init=/bin/bash` recovery shell |
| **Zsh not default** | Installed at `/usr/bin/zsh` and set with `chsh` |



---

## References
- [ArchWiki – Installation Guide](https://wiki.archlinux.org/title/Installation_guide)
- [ArchWiki – LightDM](https://wiki.archlinux.org/title/LightDM)
- [ArchWiki – Zsh](https://wiki.archlinux.org/title/Zsh)
- [ArchWiki – OpenSSH](https://wiki.archlinux.org/title/OpenSSH)
