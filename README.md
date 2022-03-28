# TELENOR Icotera-i4882

## Project is on hold. Broke the NAND.


#### Trying to get root in my spare time. I am an totally newbie on this but it is fun to learn new things. And i'm writing a little random just to get it out.

The router has 2 UART, one for quantenna chipset and the other for Realtek main CPU (on newer pcb versions the uart pins are not soldered, haven't tried solder them yet need a backup router first.)

Haven't found how to interrupt U-Boot on Quantenna UART except short circuit pin 16 and 17 on Winbond TSOP48 chip when kernel is loading giving me a shell. Problem is that watchdog will reboot every 12 seconds or something. So cant dump
the NAND from console.

Just before the router broke down i could interrupt realtek UART U-boot pressing reset button and pressing CTRL+C at the right time. (Autoboot is set to -1 i think.) Got an password prompt then the router died.

Never change TFTP serverIP on Quantenna UART,i did that and could never recover from it. But it gave me an login prompt on the other UART afterwards. No luck with username/password there.

My thought with changing TFTP serverIP was because the 12 second reboot i would be able to download the firmware faster than sitting for hours getting bit by bit with "MD".






### Some info gathered.

##### spi_flash layout
appid   start           len             jffs2   ddescriptor
  0     00001000        0001f000        0       uboot
  1     00020000        00020000        0       uboot_env
  2     00040000        00020000        0       uboot_env_bak
  5     00060000        00080000        0       cal_dat

####  SPI flash info:
          name             : w25q16FW
          jedec_id         : 0xef6015
          sector size      : 65536
          number of sector : 32
          frequency        : 40000000
          flags            : 0x2
          lock             : 10000000000000000000000000000000

####   Current board config:
                  ID:     65535
                  Name:   U84AXP1_2500BASE-X_PHY
                  DDR:    DDR3_32_WINBOND 800MHz 256M
                  EMAC0:
                  EMAC1:  <NULL>
                  RFPA:   QTN_RUBY_BRINGUP_RWPA
                  RGMII:  0x0
                  SPI1:   Disabled
                  UART1:  Enabled
                  PCIe:   Disabled
