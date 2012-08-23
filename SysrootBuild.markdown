![rpm structure](https://chart.googleapis.com/chart?cht=gv&chs=500x300&chl=digraph%20G%20{%20upstream_sources%20-%3E%20sysroot%20[weight=8];%20sysroot%20-%3E%20gcc_rpm%20sysroot%20-%3E%20devel_rpm%20sysroot%20-%3E%20devel_static_libraries_rpm%20sysroot%20-%3E%20orig_flash_files_rpm%20gcc_rpm%20-%3E%20work_area%20devel_rpm%20-%3E%20work_area%20devel_static_libraries_rpm%20-%3E%20work_area%20[style=dotted];%20work_area%20-%3E%20flash_files%20})

To get started:

    git clone git@gitorious.org/cambridge/klaatu-manifests.git
    mkdir test
    cd test
    ../klaatu-manifests/scripts/fullbuild android-4.1.1_r4
    source build/envsetup.sh
    lunch full_maguro-userdebug
    make -j33
    ../klaatu-manifests/scripts/buildrpm


Reference output images are placed in:
   * [http://code.google.com/p/klaatu/downloads/list](http://code.google.com/p/klaatu/downloads/list)


