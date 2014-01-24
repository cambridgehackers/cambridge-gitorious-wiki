Kivy for Klaatu Manual Build and installation
---------------------------------------------

There is now an option to include kivy in the klaatu build. These
instructions are for manual build and deployment.

First, set up this:
http://python-for-android.readthedocs.org/en/latest/prerequisites/

Then, check out p4a:

    git clone https://github.com/kivatu/python-for-android.git

then build:

    cd python-for-android
    ./distribute.sh -m "pil kivy"

Installing on a device
----------------------

    cd dist/default
    adb push python-install /data/python-install
    adb push private /data/python-private
    adb push libs/armeabi /data/python-install/lib
    adb shell

Set up environment variables on the device:

    export EXTERNAL_STORAGE=/mnt/sdcard
    export LANG=en
    export PYTHONPATH=/data/python-install/lib:/data/python-install/lib/python2.7:/data/python-install/lib/python2.7/site-packages
    export TEMP=/mnt/storage/com.googlecode.pythonforandroid/extras/python/tmp
    export PYTHON_EGG_CACHE=$TEMP
    export PYTHONHOME=/data/python-install
    #export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/data/python-install/lib:/data/python-install/lib/python2.7/lib-dynload:/data/python-install/lib/python2.7:/data/python-private/lib/python2.7
    export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/data/python-install/lib:/data/python-install/lib/python2.7:/data/python-install/lib/python2.7/lib-dynload:/data/python-install/lib/python2.7/site-packages
    export ANDROID_ARGUMENT=1
    #ANDROID_PRIVATE should point to libpymodules.so (due to custom-loader.patch)
    export ANDROID_PRIVATE=/data/python-private 
    export ANDROID_APP_PATH=/data/app
    export PATH=$PATH:/data/python-install/bin
    export KIVY_WINDOW=egl_klaatu

now run kivy apps!

configuring touch
-----------------

if touch doesn’t work, edit the config file and specify your touch
device under [input]

<code>\
/data/temp/.kivy/config.ini\
</code>
