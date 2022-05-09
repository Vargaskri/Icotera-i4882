# TELENOR Icotera-i4882



#### Trying to get root in my spare time. I am an totally newbie on this but it is fun to learn new things. 





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
