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
we could build:
```
cd ${GOPATH}/src/github.com/robertberger/gobyexample/03-variables
```
```
${TARGET_PREFIX}go build variables.go
```
and run:
depends on arch, but I have some x86 qemu so if it's all statically linked it might work:
```
${TARGET_PREFIX}go run variables.go
```
or
```
./variables
```
and debug:
```
dlv exec ./variables
```
in the debugger:
```
Type 'help' for list of commands.
(dlv) b main.main
Breakpoint 1 set at 0x499098 for main.main() ./variables.go:9
(dlv) c
> main.main() ./variables.go:9 (hits goroutine(1):1 total:1) (PC: 0x499098)
Warning: debugging optimized function
     4:
     5: package main
     6:
     7: import "fmt"
     8:
=>   9: func main() {
    10:
    11:         // `var` declares 1 or more variables.
    12:         var a = "initial"
    13:         fmt.Println(a)
    14:
(dlv) n
> main.main() ./variables.go:13 (PC: 0x4990af)
Warning: debugging optimized function
     8:
     9: func main() {
    10:
    11:         // `var` declares 1 or more variables.
    12:         var a = "initial"
=>  13:         fmt.Println(a)
    14:
    15:         // You can declare multiple variables at once.
    16:         var b, c int = 1, 2
    17:         fmt.Println(b, c)
    18:
(dlv) whatis a
string
(dlv) c
initial
1 2
true
0
apple
Process 1067570 has exited with status 0
(dlv) quit
```
