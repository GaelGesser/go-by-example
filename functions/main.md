# 11 Functions

Funções são muito importantes em Go

Segue exemplos de funções para aprendermos


Aqui temos uma função que recebe 2 parametros int e retorna um int
```go
  func plus(a int, b int) int {
      return a + b
  }

  // plus(2, 2)
  // 4
```

Em go as funções exigem retornos explícitos.

Quando temos varios parametros com tipagem igual podemos omitir o nome do tipo para os parametros de mesmo tipo até o último parâmetro, que declara o tipo segue exemplo:

```go
  func plusPlus(a, b, c int) int {
      return a + b + c
  }
```

para chamar uma função usamos da maneira padrão com `nome(args)`

## 11.1 Multiple Return Values

Em go as funções tem suporte a multiplos retornos 
segue exemplo: 

```go
  package main

  import "fmt"

  func vals() (int, int) {
      return 3, 7
  }

  func main() {

      a, b := vals()
      fmt.Println(a)
      fmt.Println(b)

      _, c := vals()
      fmt.Println(c)
  }
```

## 11.2 Variadic Functions

Esse tipo de função pode receber qualquer número de parametros, segue exemplo:

```go
  package main

  import "fmt"

  func sum(nums ...int) {
      fmt.Print(nums, " ")
      total := 0

      for _, num := range nums {
          total += num
      }
      fmt.Println(total)
  }

  func main() {

      sum(1, 2)
      sum(1, 2, 3)


      // Podemos passar um slice completo usando o exemplo
      nums := []int{1, 2, 3, 4}
      sum(nums...)
  }
```

## 11.3 Closures

Go tem suporte a funções anonimas, que pode formar closures.


A função `intSeq` retorna outra função, que definimos anonimamente no corpo de `intSeq`. A função retornada realiza um fechamento sobre a variável `i` para formar um fechamento.

```go
  package main

  import "fmt"

  func intSeq() func() int {
      i := 0
      return func() int {
          i++
          return i
      }
  }

  func main() {

      nextInt := intSeq()

      fmt.Println(nextInt()) // 1
      fmt.Println(nextInt()) // 2
      fmt.Println(nextInt()) // 3

      newInts := intSeq()
      fmt.Println(newInts()) // 1
  }

  // $ go run closures.go
  // 1
  // 2
  // 3
  // 1
```

## 11.4 Recursion

Uma função Recursion é uma função que chama a si mesma.

```go
  package main

  import "fmt"

  func fact(n int) int {
      if n == 0 {
          return 1
      }
      return n * fact(n-1)
  }

  func main() {
      fmt.Println(fact(7))

      var fib func(n int) int

      fib = func(n int) int {
          if n < 2 {
              return n
          }

          return fib(n-1) + fib(n-2)
      }

      fmt.Println(fib(7))
  }

  // $ go run recursion.go 
  // 5040
  // 13
```