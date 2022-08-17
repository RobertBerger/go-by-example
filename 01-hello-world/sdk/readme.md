# Toolchain in cooker mode

Source the build environment:

```
source <sdk environment script>
```
e.g.
```
source /workdir/build/imx6q-phytec-mira-rdk-nand-wic-master/tmp/deploy/images/imx6q-phytec-mira-rdk-nand/environment-setup-armv7at2hf-neon-resy-linux-gnueabi
```

```
mkdir -p /workdir/sources/go-experiments
export GOPATH="/workdir/sources/go-experiments"
```
Please note that `go install` downloads and installs packages and dependencies
```
${TARGET_PREFIX}go install github.com/robertberger/gobyexample/01-hello-world@latest
```

```
tree $GOPATH
```
```
/workdir/sources/go-experiments
├── bin
│   └── linux_arm
│       └── 01-hello-world
└── pkg
    ├── mod
    │   ├── cache
    │   │   └── download
    │   │       ├── github.com
    │   │       │   └── robertberger
    │   │       │       └── gobyexample
    │   │       │           └── @v
    │   │       │               ├── list
    │   │       │               ├── v0.0.0-20210321153134-25d86941ed57.info
    │   │       │               ├── v0.0.0-20210321153134-25d86941ed57.lock
    │   │       │               ├── v0.0.0-20210321153134-25d86941ed57.mod
    │   │       │               ├── v0.0.0-20210321153134-25d86941ed57.zip
    │   │       │               └── v0.0.0-20210321153134-25d86941ed57.ziphash
    │   │       └── sumdb
    │   │           └── sum.golang.org
    │   │               ├── lookup
    │   │               │   └── github.com
    │   │               │       └── robertberger
    │   │               │           └── gobyexample@v0.0.0-20210321153134-25d86941ed57
    │   │               └── tile
    │   │                   └── 8
    │   │                       ├── 0
    │   │                       │   └── x046
    │   │                       │       └── 640.p
    │   │                       │           └── 122
    │   │                       ├── 1
    │   │                       │   └── 182.p
    │   │                       │       └── 48
    │   │                       └── 2
    │   │                           └── 000.p
    │   │                               └── 182
    │   └── github.com
    │       └── robertberger
    │           └── gobyexample@v0.0.0-20210321153134-25d86941ed57
    │               ├── 00-SDK-with-yocto
    │               │   └── readme.md
    │               ├── 01-hello-world
    │               │   ├── hello-world.go
    │               │   └── sdk
    │               │       └── readme.md
    │               ├── 02-values
    │               │   └── values.go
    │               ├── 03-variables
    │               │   ├── sdk
    │               │   │   └── readme.md
    │               │   └── variables.go
    │               ├── 04-constants
    │               │   └── constants.go
    │               ├── 05-for
    │               │   └── for.go
    │               ├── 06-if-else
    │               │   └── if-else.go
    │               ├── 07-switch
    │               │   └── switch.go
    │               ├── 08-arrays
    │               │   └── arrays.go
    │               ├── 09-slices
    │               │   └── slices.go
    │               ├── 10-maps
    │               │   └── maps.go
    │               ├── 11-range
    │               │   └── range.go
    │               ├── LICENSE
    │               ├── Readme.md
    │               └── scripts
    │                   └── push-upstream.sh
    └── sumdb
        └── sum.golang.org
            └── latest

44 directories, 29 files

```
we could run:
depends on arch, but I have some x86 qemu so if it's all statically linked it might work:
```
${TARGET_PREFIX}go run hello-world.go
```

for a cross compiled binary we copy it over to the target
