   * The Android Java UI is configured (4.1.1) from:
      * frameworks/base/core/res/res/values/config.xml  (for example: config_showNavigationBar turns on the 'on screen' navigation buttons)
   * The initial layout/defaults for the screen are done in:
      * frameworks/base/policy/src/com/android/internal/policy/impl/PhoneWindowManager.java:setInitialDisplaySize()

   * Filesystems
   * Encryption of /data is done by:
      * system/vold/cryptfs.c:cryptfs_enable()
   * It looks like setting "ro.crypto.state=unencrypted" might turn this off.