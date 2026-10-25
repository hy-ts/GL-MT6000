# GL-MT6000 custom OpenWrt firmware builder

This repository automates the process of building OpenWrt custom firmware images for my Flint 2 (GL-MT6000) router, based on my preferences and [cjom](https://github.com/cjom/GL-MT6000)'s work.

You should not use the firmwares released in this repository unless you have the same preferences/needs.
Instead, make a fork and adapt to your needs.

Compared to his custom firmware, this firmware adds:
- LLDP
- Usteer

Notes:
- **The purpose of this firmware is exclusively Access Point operation**.
- If you fork this repository, the script will be adapted to look for upgrades in your repository.
- The text output of upgrade_custom_openwrt script will show both in terminal and system logs.

## Acknowledgements

- The OpenWrt project for providing the foundation for this firmware build and support of [GL.iNet GL-MT6000](https://openwrt.org/toh/gl.inet/gl-mt6000) router.
- The community over at the [OpenWrt forum](https://forum.openwrt.org/t/mt6000-custom-build-with-luci-and-some-optimization-kernel-6-12-x/185241) for their valuable contributions and resources. 
- [pesa1234](https://github.com/pesa1234) for his [MT6000 custom builds](https://github.com/pesa1234/MT6000_cust_build).
- [cjom](https://github.com/cjom) for his [MT6000 custom builds](https://github.com/cjom/GL-MT6000).
