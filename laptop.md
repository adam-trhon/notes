
Specs
=====
- Lenovo Legion 5 16IRX9
- [Manufacturer Page](https://psref.lenovo.com/Product/Legion/Legion_5_16IRX9)
- [Shop Page](https://www.alza.cz/lenovo-legion-5-16irx9-luna-grey-kovovy-podlozka-pod-mys-d9834544.htm)
- Links from Vilem:
  - [Tips for Linux on Lenovo laptops](https://github.com/cszach/linux-on-lenovo-legion)
  - [Utility driver](https://github.com/johnfanv2/LenovoLegionLinux) (https://github.com/johnfanv2/LenovoLegionLinux/issues/163 issue of adding my laptop)
  - [EnvyControl for switching GPU mode](https://github.com/bayasdev/envycontrol)

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
    
