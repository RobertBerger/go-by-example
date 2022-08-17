# Intro

Of course, as usual, I would recommend to use my build framework[1], since this is also what I use to build.

[1] https://rlbl.me/build-fw-tube

# Toolchain in cooker mode

Like this you build a toolchain in cooker mode:

```
bitbake core-image-minimal-base-tig-plus-plus-prebuilt
```

```
bitbake meta-ide-support
bitbake build-sysroots
```

Source the build environment:
```
source /workdir/build/imx6q-phytec-mira-rdk-nand-wic-master/tmp/deploy/images/imx6q-phytec-mira-rdk-nand/environment-setup-armv7at2hf-neon-resy-linux-gnueabi 
```

# Go toolchain (stand alone)

Like this you build the go toolchain:

```
bitbake meta-go-toolchain
```

You can install it after it finished building.

e.g.

```
./resy-container-glibc-x86_64-meta-go-toolchain-core2-64-container-x86-64-toolchain-3.2+snapshot.sh
```
```
Resy Container (Reliable Embedded Systems (libc) Container Reference Distro) SDK installer version 3.2+snapshot
===============================================================================================================
Enter target directory for SDK (default: /opt/resy-container/3.2+snapshot):
You are about to install the SDK to "/datastore/opt/resy-container/3.2+snapshot". Proceed [Y/n]? Y
Extracting SDK......................................................................................done
Setting it up...done
SDK has been successfully set up and is ready to be used.
Each time you wish to use the SDK in a new shell session, you need to source the environment setup script e.g.
 $ . /datastore/opt/resy-container/3.2+snapshot/environment-setup-core2-64-resy-linux
```
