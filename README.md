# libhdhomerun

This is the development library for the SiliconDust HD HomeRun.

The code can be directly cloned from Git:

```
git clone https://github.com/rymitch/libhdhomerun.git
cd libhdhomerun
./autogen.sh
```

Note that GNU Autoconf >=2.63, Automake >=1.11 and Libtool >=2.2.6 are required when building from a Git clone.

To build the library:

```
./configure
make
make install
```

## Branches

The [vendor](https://github.com/rymitch/libhdhomerun/tree/vendor) branch tracks the original, unmodified source code releases from https://www.silicondust.com/support/downloads/.

The [master](https://github.com/rymitch/libhdhomerun/tree/master) branch extends the vendor branch to include an autotools wrapper and minor changes to support the autotools build.
