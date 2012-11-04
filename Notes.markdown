   * The Android Java UI is configured (4.1.1) from:
      * frameworks/base/core/res/res/values/config.xml  (for example: config_showNavigationBar turns on the 'on screen' navigation buttons)
   * The initial layout/defaults for the screen are done in:
      * frameworks/base/policy/src/com/android/internal/policy/impl/PhoneWindowManager.java:setInitialDisplaySize()

   * Filesystems
   * Encryption of /data and /system is requested by:
      * frameworks/base/core/java/android/os/Environment.java:isEncryptedFilesystemEnabled()
   * Encryption of /data is done by:
      * system/vold/cryptfs.c:cryptfs_enable()
   * It looks like setting "persist.security.efs.enabled=false" might turn this off.

   * Mapping of linux keycodes to Android keys is done in *.kl files.  For example:
      * device/asus/grouper/gpio-keys.kl

   * Configuration of things like 'use software emulation for opengles' are in BoardConfig.mk files.

   * Capture a baseline with repo:
      * repo manifest -r -o oldbaseline.xml