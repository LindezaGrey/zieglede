# Customized OpenWRT Image for GL.iNet GL-AR750

[![Generic badge](https://img.shields.io/badge/Model-GL.iNet%20GL&#x2212;AR750-yellow.svg)](https://www.gl-inet.com/products/gl-ar750/)
[![Generic badge](https://img.shields.io/badge/builds-yes-brightgreen.svg)](https://github.com/LindezaGrey/zieglede/blob/master/openwrt-ar71xx-generic-gl-ar750-squashfs-sysupgrade.bin)
[![BADGINATOR](https://img.shields.io/badge/badges-2-brightgreen.svg?style=flat)](https://github.com/LindezaGrey/zieglede)

## Purpose

This is a fork from the vanilla [OpenWRT](https://github.com/openwrt/openwrt) firmware. This firmware is a replacement for the stock firmware. It is already preconfigured so it can be used out of the box. You should use this firmware if you want to have an up-to-date OpenWRT installation and don't want the preinstalled and modded firmware of the manufacturer or just don't trust the stock firmware. This firmware comes with the following features enabled:

* working Freeradius3 server (default user: guest, password: secret) with WPA2-EAP protected wifi (enterprise)
* Samba Server
* Block mount (automatic mount of USB drives)
* OpenVPN
* LuCi (with https)
* 2.4 GHz Wifi
* 5 GHz Wifi
* Guest Network
* DNS based Adblocker for all devices in the network
* SQM QoS module for traffic shaping and better latency
* Bandwitdh monitor
* Wifi schedule
* OpenSSH server
* Other useful tools: nano, wget, rsync

## Flashing the image via LuCi

On your stock firmware you can navigate to the LuCi interface and simply flash this [firmware](https://github.com/LindezaGrey/zieglede/blob/master/openwrt-ar71xx-generic-gl-ar750-squashfs-sysupgrade.bin). Make sure you disable the "Keep settings" checkbox.

## Building the image by yourself
First install buildtools on your preferred linux machine

```
sudo apt-get install gcc binutils bzip2 flex python perl make grep unzip gawk subversion libz-dev
```

Run

```
./scripts/feeds update -a
```

to get all the latest package definitions
defined in feeds.conf / feeds.conf.default respectively
and

```
./scripts/feeds install -a
```

to install symlinks of all of them into
package/feeds/.

Use

```
make menuconfig
```

to configure your image.
If there are missing packages, install them.
Simply running
```
make
```
will build your firmware.