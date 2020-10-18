1. Connect to internet
   1. Set up netctl
2. Make file system
   1. Format and activate file system


# Connect to internet

- [Check network device](https://wiki.archlinux.org/index.php/Network_configuration/Wireless#Device_driver)
- [iwctl](https://wiki.archlinux.org/index.php/Iwd#iwctl)

```bash
lspci -k # Hardware
ip link  # Show interfaces

ip link set `interface` up # Set up the wifi
ip link set wlan0 up
```

```bash
iwctl
station `device` scan # Scan networks
station `device`  get-networks
station `device` connect `SSID`
```

