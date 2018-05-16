# Kong is a command-line parser for Go

It parses a command-line into a struct. eg.

```go
package main

import "github.com/alecthomas/kong"

var CLI struct {
  Rm struct {
    Force     bool `help:"Force removal."`
    Recursive bool `help:"Recursively remove files."`

    Paths []string `help:"Paths to remove." type:"path"`
  } `help:"Remove files."`

  Ls struct {
    Paths []string `help:"Paths to list." type:"path"`
  } `help:"List paths."`
}

func main() {
  kong.Parse(&CLI)
}
```