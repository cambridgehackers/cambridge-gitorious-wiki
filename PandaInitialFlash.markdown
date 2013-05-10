    sudo usbboot bootloader.bin
    sudo fastboot oem format
    sudo fastboot flash xloader.bin
    sudo fastboot flash bootloader.bin

Detailed information can be found at **device/ti/panda/README** from
Android source tree.
