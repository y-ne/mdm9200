## MDM9200 Script
Scipt that allow you to connect Qualcomm MDM9200 Based 3G/LTE USB Modem to your Router with OpenWRT Firmware

## Test Device
### Router
* Model    : TP-Link TL-MR3040 v2
* Flash/RAM: 4/32 MB
* Firmware : LEDE Reboot 17.01.5
* Kernel   : 4.4.140

## Update 

[Closed Issue](https://github.com/y-ne/mdm9200/issues/1)

hi, it's been a while since i had any work with anything that related to old build of openwrt or cheap LTE dongles.

to be honest. i'd recommend you to just get anything that had ether port so you can interface it as uplink via `eth` on your openwrt build. you'll have better experience than this.

this script was just to change the mode of the `mdm9200` based dongle from `usb mass storage` to `qmi/mbim` by altering the `usbmode` of the vendor so we can use it on interfaces as WWAN like normal with `kmod-usb-net-qmi` or `kmod-usb-net-qmi`.

if my memory serves me right. you'd just have to copy the file inside `modules.d` to `/etc/modules.d` and `mdm9200.json` to `/etc/` and add the line `usbmode -v -s -c /etc/mdm9200.json` to `/etc/rc.local` so it will executed at boot.
