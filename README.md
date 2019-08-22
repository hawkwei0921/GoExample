# GoExample

### A. Create a repository on GitHub
New repository without README.md on GitHub
```
git clone https://github.com/hawkwei0921/GoExample.git
```

### B. Initialize a new module for Go
```
go mod init github.com/hawkwei0921/GoExample.git
```

### C. Write code
Write your code:
```
$ cat <<EOF > hello.go
package main

import (
    "fmt"
    "rsc.io/quote"
)

func main() {
    fmt.Println(quote.Hello())
}
EOF
```
### D. Build and Run

ARM Android: Build and run on Android: ( default is 64-bit ELF file only run on Linux )
```
$ env GOOS=linux GOARCH=arm go build -o hello
$ adb root
$ adb push hello /data/
$ adb shell
Under Android Device Shell
$ cd /data
$ ./hello

Hello, world.
```

PC Linux: Build and run on Linux: ( default is 64-bit ELF file only run on Linux )
```
$ go build -o hello
$ ./hello

Hello, world.
```

The `go.mod` file was updated to include explicit versions for your dependencies, where `v1.5.2` here is a [semver](https://semver.org) tag:
```
$ cat go.mod

module github.com/hawkwei0921/GoExample.git

require rsc.io/quote v1.5.2
```
### E. Upload to GitHub
```
git add <file1> <file2> ... <fileN>
git commit -a
git push
Input GitHub Account and Password
```
