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

