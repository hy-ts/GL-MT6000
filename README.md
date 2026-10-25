# GL-MT6000 custom OpenWrt firmware builder

This repository automates the process of building OpenWrt custom firmware images for my Flint 2 (GL-MT6000) router, based on my preferences and [cjom](https://github.com/cjom/GL-MT6000)'s work.

You should **not use** the firmwares released in this repository unless you have the same preferences/needs.
Instead, **make a fork and adapt to your needs**.

Read [this topic](https://forum.openwrt.org/t/mt6000-custom-build-with-luci-and-some-optimization-kernel-6-12-x/185241) in OpenWrt's forum to learn the details about pesa1234's customizations.

Compared to his custom firmware, this firmware adds:
- **WiFi UCODE scripts** (faster boot)

And also:
- **REMOVED:** odhcp, upnp, iptables, avahi, samba, usb storage and probably more stuff I forgot to mention.
- Added the needed packages to use QoS script [cake-wg-pbr](https://github.com/lynxthecat/cake-wg-pbr)
- Some compiler optimizations and build hardening options (cortex-a53+crc+crypto; LTO, MOLD, and more).
- Some debug and kernel stuff removed.
- [`upgrade_custom_openwrt`](files/usr/bin/upgrade_custom_openwrt) script

Check the content of [`mt6000.config`](mt6000.config) for details.


## About Custom Attended Sysupgrade

Using Luci's menu "System" --> "Attended Sysupgrade" it is now possible to select and install custom firmware from GitHub.
  
<sub>Custom Attended Sysupgrade</sub>  
![Custom Attended Sysupgrade](attended-sysupgrade-custom.png)
  
<sub>Dropdown list</sub>  
![Dropdown list](attended-sysupgrade-releases.png)
  
<sub>Installing Custom Firmware</sub>  
![Installing Custom Firmware](attended-sysupgrade-installing.png)
  
<sub>GitHub repository</sub>  
![GitHub repository used](attended-sysupgrade-server.png)
  
Notes:
- if you fork this repository, this will be adapted to look for upgrades in your repository by default.

Notes:
- The installed files survive firmware upgrades.
- The text output of the installer will show both in terminal and system logs.



## About upgrade_custom_openwrt script

```
THIS IS NOW DEPRECATED, ALTHOUGHT THE SCRIPT IS STILL INCLUDED
```

I added a script to make upgrading OpenWRT super easy. Just run from a SSH terminal:
- `upgrade_custom_openwrt --now` to check if a newer firmware is available and upgrade if so.
- `upgrade_custom_openwrt --wait` to wait for clients activity to stop before upgrading.
- `upgrade_custom_openwrt --check` to check for new versions but not upgrade the router.

**IT IS NOT RECOMMENDED** to schedule the script to be executed automatically, although the script is very careful and checks sha256sums before trying to upgrade. Don't blame me if something goes wrong with scripts that **YOU** run in your router!

Notes:
- if you fork this repository, the script will be adapted to look for upgrades in your repository.
- The text output of upgrade_custom_openwrt script will show both in terminal and system logs.


## Acknowledgements

- The OpenWrt project for providing the foundation for this firmware build and support of [GL.iNet GL-MT6000](https://openwrt.org/toh/gl.inet/gl-mt6000) router.
- The community over at the [OpenWrt forum](https://forum.openwrt.org/t/mt6000-custom-build-with-luci-and-some-optimization-kernel-6-12-x/185241) for their valuable contributions and resources. 
- [pesa1234](https://github.com/pesa1234) for his [MT6000 custom builds](https://github.com/pesa1234/MT6000_cust_build).
- [cjom](https://github.com/cjom) for his [MT6000 custom builds](https://github.com/cjom/GL-MT6000).
