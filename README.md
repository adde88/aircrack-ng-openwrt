# aircrack-ng 1.2-rc5 (OpenWRT)

This repo will contain the latest source and installation files for aircrack-ng on OpenWRT.

## Getting Started

Installation (IPK) files can be found within "bin/ar71xx/packages/base" directory.  
OpenWRT-SDK Makefiles are within "package/net/aircrack-ng/" directory.

### Prerequisites

The install-files are customized for the WiFi Pineapples  
But using the Makefile with OpenWRT-SDK you can build it for any system.


### Installing

Download the IPK and transfer it to your device with your preferred terminal software.

```
opkg install aircrack-ng_1.2-rc5-1_ar71xx.ipk
opkg install aircrack-ng_1.2-rc5-1_ar71xx.ipk --dest sd
```
First line will install aircrack-ng to your local storage.  
The second will use your SD-card, preferred if you're using a Pineapple NANO.


## Built With

* [OpenWRT-SDK](http://archive.openwrt.org/chaos_calmer/15.05/ar71xx/generic/OpenWrt-SDK-15.05-ar71xx-generic_gcc-4.8-linaro_uClibc-0.9.33.2.Linux-x86_64.tar.bz2) - The OpenWRT-SDK for ar71xx devices.
