Kivy for Klaatu Manual Build and installation
---------------------------------------------

There is now an option to include kivy in the klaatu build. These
instructions are for manual build and deployment.

First, set up this:
http://python-for-android.readthedocs.org/en/latest/prerequisites/

Then, check out p4a:

    git clone https://github.com/kivatu/python-for-android_old.git

then build:

    cd python-for-android
    ./distribute.sh -m "pil kivy"

Installing on a device
----------------------

    cd dist/default
    adb push python-install /system
    adb push private /system/lib/python-private
    adb push libs/armeabi /system/lib
    adb shell

Set up environment variables on the device:

    source /system/envsetup.sh

now run kivy apps!

    python /system/share/kivy-examples/demo/touchtracer/main.py

configuring touch
-----------------

if touch doesn’t work, edit the config file and specify your touch
device under [input]

<code>\
/data/temp/.kivy/config.ini\
</code>
