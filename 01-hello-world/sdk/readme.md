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
