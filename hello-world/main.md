## 1 - Primeiro Hello World

Segue exemplo

```go

  package main

  import "fmt"

  func main() {
    fmt.Println("Hello World!")
  }

```

Em seguida rodamos esses comandos para poder executar

---
```
$ go run ./hello-word/main.go
hello world

$ go build ./hello-word/main.go
$ ls
main

$ ./main
hello world
```