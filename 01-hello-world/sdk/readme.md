```
source <sdk environment script>
```
e.g.
```
source /opt/resy-container/3.2+snapshot/environment-setup-core2-64-resy-linux
```

```
mkdir -p /home/student/projects/gatesgarth
export GOPATH="/home/student/projects/gatesgarth"
```
Please note that `go get` downloads and installs packages and dependencies
```
${TARGET_PREFIX}go get github.com/robertberger/gobyexample/01-hello-world
```

```
tree $GOPATH
```
```
/home/student/projects/gatesgarth
├── bin
│   └── 01-hello-world
└── src
    └── github.com
        └── robertberger
            └── gobyexample
                ├── 01-hello-world
                │   ├── hello-world.go
                │   └── sdk
                │       └── readme.md
                ├── 02-values
                │   └── values.go
                ├── 03-variables
                │   └── variables.go
                ├── 04-constants
                │   └── constants.go
                ├── 05-for
                │   └── for.go
                ├── 06-if-else
                │   └── if-else.go
                ├── 07-switch
                │   └── switch.go
                ├── 08-arrays
                │   └── arrays.go
                ├── 09-slices
                │   └── slices.go
                ├── 10-maps
                │   └── maps.go
                ├── LICENSE
                ├── Readme.md
                └── scripts
                    └── push-upstream.sh

17 directories, 15 files
```
we could build:
```
cd ${GOPATH}/src/github.com/robertberger/gobyexample/01-hello-world
```
```
${TARGET_PREFIX}go build hello-world.go
```
and run:
depends on arch, but I have some x86 qemu so if it's all statically linked it might work:
```
${TARGET_PREFIX}go run hello-world.go
```
