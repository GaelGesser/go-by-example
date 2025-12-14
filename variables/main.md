## 3 - Variaveis

Em go podemos declarar mais de uma variavel na mesma linha se ela for do mesmo tipo exp

```go

  var b, c = 1, 2
  // 1 2

  // OU passando o tipo tmb mas se tem valor ele já usa o tipo

  var b, c int = 1, 2
  // 1 2

```

e temos a maneira normal usando var e uma maneira `shorthand` usando := segue exemplo

```go
  var a = "initial"
  // initial
    
  var d = true
  // true

  var e int
  // 0
      
  // SHORTHAND
  f := "apple"
  // apple

  // Notei que quando criamos uma variavel como string vazia segue exmp
  blank := ""
  // O Retorno dela é vazio não mostra nada no print
```