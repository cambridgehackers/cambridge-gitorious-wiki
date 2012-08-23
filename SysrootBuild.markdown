![rpm structure](https://chart.googleapis.com/chart?cht=gv&chs=500x300&chl=digraph%20G%20{%20upstream_sources%20-%3E%20sysroot%20[weight=8];%20sysroot%20-%3E%20gcc_rpm%20sysroot%20-%3E%20devel_rpm%20sysroot%20-%3E%20devel_static_libraries_rpm%20sysroot%20-%3E%20orig_flash_files_rpm%20gcc_rpm%20-%3E%20work_area%20devel_rpm%20-%3E%20work_area%20devel_static_libraries_rpm%20-%3E%20work_area%20[style=dotted];%20work_area%20-%3E%20flash_files%20})

Preparation:

To run this build on Ubuntu 11.04:
    sudo apt-get install git bison flex lib32gcc1 lib32z1-dev lib32stdc++6 ia32-libs lib32ncursesw5 libxml2-utils

On Ubuntu 10.04, this has been recommended:
    sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev ia32-libs x11proto-core-dev libx11-dev lib32readline5-dev lib32z-dev libxml-simple-perl

Install repo:
    curl http://android.git.kernel.org/repo >~/bin/repo
    chmod a+x ~/bin/repo
    export PATH=~/bin:$PATH

To get started:

    git clone git://gitorious.org/cambridge/klaatu-manifests.git
    mkdir test
    cd test
    ../klaatu-manifests/scripts/fullbuild android-4.1.1_r4
    source build/envsetup.sh
    lunch full_maguro-userdebug
    make -j33
    ../klaatu-manifests/scripts/buildrpm      (assumes rpmbuild exists as a tool)

Reference output images are placed in:
   * [http://code.google.com/p/klaatu/downloads/list](http://code.google.com/p/klaatu/downloads/list)


