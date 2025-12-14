## 11 Functions

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

