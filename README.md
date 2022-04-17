
# rr268xx

** 17.04.2022: Rudimentary legacy-dump after ~10 years, for historical purposes without .tar.gz -files **
** 16.07.2012: Just get v1.8 driver **

Driver for RocketRAID 268x (v1.4/v1.6) with kernel support >2.6.37.
Disclaimer: No guarantees whatsoever, these might blow up your computer/corrupt data/anything.
Made originally for my own use only, use at your own risk. You've been warned.


rr268x-linux-src-v1.4-091124-1558.tar.gz
Version 1.4 driver for RocketRaid 268x
Fetched from http://www.highpoint-tech.cn/BIOS_Driver/page/rr2680.htm (5.11.2011)

rr268x-linux-src-v1.4.patch
Patch for RocketRAID 268x version 1.4 driver to enable support for kernels greater than version 2.6.37 (also 3.x).
Tested: Ubuntu 11.04 with kernel 2.6.38-12-server (amd64)

rr268x-linux-src-v1.6-legacy_single-110316-1107.tar.gz
Version 1.6 driver for RocketRaid 268x
Fetched from http://www.highpoint-tech.cn/China_new/rr2600_downloadc.htm (5.11.2011)

rr268x-linux-src-v1.6.patch
Patch for RocketRAID 268x version 1.6 driver to enable support for kernels greater than version 2.6.37 (also 3.x).
Tested: Ubuntu 11.04 with kernel 2.6.38-12-server (amd64)


Usage instructions (Ubuntu, probably works for others also):
Download rr268x-linux-src-v1.<the version you want>.tar.gz (from here or from the manufacturers site).
Download rr268x-linux-src-v1.<the version you want>.patch (from here).
Extract .tar.gz, copy patch to the same folder.
Open terminal, if you haven't already done so, go to that folder where you've extracted files and type:
patch -p1 -i rr268x-linux-src-v1.<the version you want>.patch

Read README to figure out how to compile that kernel module, or use commands below:
cd product/rr2680/linux/ (v1.4) or cd product/rr2680/linuxls/ (v1.6)
make
make install


Known problems with both drivers:
hddtemp: segfaults
hdparm: works for me (-i/-I to retrieve information)
smartctl: passthrough doesn't work: "Device does not support SMART"

Todo:
Check if it actually works under Oneiric (3.x kernel) or Maveric (<2.6.37 kernel) - it compiles successfully.
