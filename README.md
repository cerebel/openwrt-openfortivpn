# openwrt-openfortivpn
OpenWRT package for [openfortivpn: A Fortinet (and Ruijie) compatible client for PPP+SSL VPN tunnel services](https://github.com/adrienverge/openfortivpn)

## Build
Example for ar71xx and trunk.
```

########### old
#wget http://downloads.openwrt.org/snapshots/trunk/ar71xx/generic/OpenWrt-SDK-ar71xx-generic_gcc-4.8-linaro_musl-1.1.11.Linux-x86_64.tar.bz2
#tar jxf OpenWrt-SDK-ar71xx-generic_gcc-4.8-linaro_musl-1.1.11.Linux-x86_64.tar.bz2
#cd OpenWrt-SDK-ar71xx-generic_gcc-4.8-linaro_musl-1.1.11.Linux-x86_64/package
########### 

# https://archive.openwrt.org/snapshots/trunk/ar71xx/generic/OpenWrt-SDK-ar71xx-generic_gcc-5.3.0_musl-1.1.16.Linux-x86_64.tar.bz2
vSDK=OpenWrt-SDK-ar71xx-generic_gcc-5.3.0_musl-1.1.16.Linux-x86_64

wget http://downloads.openwrt.org/snapshots/trunk/ar71xx/generic/${vSDK}.tar.bz2
tar jxf ${vSDK}.tar.bz2
cd      ${vSDK}/package

## openwrt part https://openwrt.org/docs/guide-developer/build-system/use-buildsystem
## Download and update the sources
git clone https://github.com/excelwang/openwrt-openfortivpn openfortivpn


cd ..
./scripts/feeds update base
./scripts/feeds install libopenssl resolveip ppp
make package/openfortivpn/compile V=s
```
