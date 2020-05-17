# u-boot-v3-camera
add support of allwinner V3 cpu action camera to mainline u-boot


** WIP **
Currently only SPL part of uboot runs normally.
from FEL:

```
U-Boot SPL 2020.07-rc2-gb187c4b2 (May 17 2020 - 16:22:18 +0300)
DRAM: 128 MiB
Trying to boot from FEL
**HANG**
```

from MMC:

```
U-Boot SPL 2020.07-rc2-gb187c4b2 (May 17 2020 - 16:22:18 +0300)
DRAM: 128 MiB
Trying to boot from MMC1
**HANG**
```

from SPI:

```
U-Boot SPL 2020.07-rc2-gb187c4b2 (May 17 2020 - 16:22:18 +0300)  
DRAM: 128 MiB
Trying to boot from SPI
**HANG**
```


## compile & run
compile:

<code>
make CROSS_COMPILE=arm-linux-gnu- v3s_camera_defconfig

make CROSS_COMPILE=arm-linux-gnu- 
</code>

run:
put device in FEL mode by pressing Vol-Down button when poweron, then

<code>
sunxi-fel uboot u-boot-sunxi-with-spl.bin
</code>

or just write to sdcard:

<code>
dd if=u-boot-sunxi-with-spl.bin of=/dev/SDCARD bs=1024 seek=8
</code>


![pinout](https://github.com/ktkd/u-boot-v3-camera/raw/master/camera_ttl.jpg)
