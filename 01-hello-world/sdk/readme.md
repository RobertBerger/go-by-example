```
source <sdk environment script>
```
```
mkdir -p /home/student/projects/dunfell
GOPATH="/home/student/projects/dunfell"
```
```
${TARGET_PREFIX}go get github.com/robertberger/gobyexample/01-hello-world
```

```
student@e450-tr1:~/projects/dunfell$ tree $GOPATH
```
```
/home/student/projects/dunfell
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
                ├── COPYING
                ├── Readme.md
                └── scripts
                    └── push-upstream.sh

8 directories, 6 files
```
```
cd ${GOPATH}/src/github.com/robertberger/gobyexample/01-hello-world
```
depends on arch, but I have some x86 qemu so if it's all statically linked it might work:
```
${TARGET_PREFIX}go run hello-world.go
```
```
${TARGET_PREFIX}go build hello-world.go
```
