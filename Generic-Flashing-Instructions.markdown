Generic steps of building and flashing on arbitrary hardware
------------------------------------------------------------

-   Get unlocked device
-   Replace bootloader with one that is built with ‘fastboot’ support
    (lk for example).
    -   rewriting bootloader (and partition table) may require
        additional JTAG hardware and device JTAG support.
-   Get AOSP or vendor AOSP branch
-   Get vendor binaries (e.g. Qualcomm) for target chipset
-   Get any Nokia specific drivers (display, touch, camera, and other
    custom peripherals)
    -   Device driver/support may require modification of both the
        kernel and bootloader
-   Build OS using custom build manifest that incorporates vendor
    binaries and Nokia specific drivers. Recommend using build scripts
    on Jenkins server.
-   Flash custom OS images into device, using fastboot tool.

    adb reboot-bootloader
    fastboot flash system.img
    fastboot flash userdata userdata.img

    -   If there is a known way to get back to fastboot (key
        combinations), then the boot image (kernel) can also be flashed

        fastboot flash boot boot.img

    -   Otherwise, load boot image in memory only

        fastboot boot boot.img
    -   For the first flash, the persist and cache images should also be
        written

        fastboot flash persist persist.img
        fastboot flash cache cache.img

