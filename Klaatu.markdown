Klaatu
------

Klaatu is a minimal linux system containing AOS kernel, HAL and low
level daemons. With other AOS systems, several services depended on the
Java engine (Dalvik). As the Klaatu system contains no Java engine, some
additional services (daemons) are required to create a fully functional
system.

-   wifi/networking
-   bluetooth
-   power management
-   messaging

One of several reference UI’s will be available to demonstrate the
system:

-   Headless (command line only)
-   Qt
-   Webkit
-   Native OpenGLES interface

### Basic Klaatu architecture

    _____________________________________________________________________________________________________
          [ example UI ]
    _____________________________________________________________________________________________________
                                     ( binder interface )
               [ klaatu_qmlscene ]   [ klaatu_phoneservice ] [ klaatu_wifiservice ] [klaatu_powermanager]
    _____________________________________________________________________________________________________
    [ binder ] [ surface flinger ]   [ rild]                 [ wpa_supplicant ]
    _____________________________________________________________________________________________________
    android hal libs/daemons (hw support)
    _____________________________________________________________________________________________________
    android kernel (hw support)
    _____________________________________________________________________________________________________
