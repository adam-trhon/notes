
Specs
=====
- Lenovo Legion 5 16IRX9
- [Manufacturer Page](https://psref.lenovo.com/Product/Legion/Legion_5_16IRX9)
- [Shop Page](https://www.alza.cz/lenovo-legion-5-16irx9-luna-grey-kovovy-podlozka-pod-mys-d9834544.htm)
- Links from Vilem:
  - [Tips for Linux on Lenovo laptops](https://github.com/cszach/linux-on-lenovo-legion)
  - [Utility driver](https://github.com/johnfanv2/LenovoLegionLinux) (https://github.com/johnfanv2/LenovoLegionLinux/issues/163 issue of adding my laptop)
  - [EnvyControl for switching GPU mode](https://github.com/bayasdev/envycontrol)
 
NVIDIA Card
===========
- Abandoned thread with some useful tips: https://bbs.archlinux.org/viewtopic.php?id=293100
- Random article about Wayland on NVidia: https://www.maketecheasier.com/wayland-work-with-nvidia-graphics-cards/
- Reddit thread about NVidia support (v545, there is v550 now): https://www.reddit.com/r/linux_gaming/comments/1arl2yg/comment/kqkw2xi/

NVIDIA PRIME
------------
- https://wiki.archlinux.org/title/PRIME#PRIME_render_offload

      sudo pacman -S nvidia-prime
      # installs Packages (4) egl-wayland-2:1.1.13-1  eglexternalplatform-1.1-2  nvidia-utils-550.67-1  nvidia-prime-1.0-4

      sudo pacman -R xf86-video-nouveau
      sudo pacman -S nvidia

  - `nvidia nvidia_modeset nvidia_uvm nvidia_drm` to MODULES in /etc/mkinitcpio.conf
  - `sudo mkinitcpio -P`
  - `nvidia-drm.modeset=1` to GRUB_CMDLINE_LINUX_DEFAULT in /etc/default/grub
  - `sudo grub-mkconfig -o /boot/grub/grub.cfg`
  

Bluetooth/Sound
===============

    sudo pacman -S bluez bluez-utils
    sudo systemctl start bluetooth
    bluetoothctl
    bluetoothctl# power on
    bluetoothctl# scan on
    bluetoothctl# devices
    bluetoothctl# pair 38:18:4C:19:E2:7C # Failed to connect: org.bluez.Error.Failed br-connection-profile-unavailable

    sudo pacman -S pulseaudio-bluetooth
    pulseaudio -k # from https://wiki.archlinux.org/title/Bluetooth#Audio

System Setup
============
Steam Error 105
---
Fix it by setting up /etc/resolv.conf ([source](https://github.com/ValveSoftware/steam-for-linux/issues/10550)):

    ln -sf ../run/systemd/resolve/stub-resolv.conf /etc/resolv.conf

    

    
