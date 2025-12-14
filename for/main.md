## 5 - For / Loops

For é o unico construtor de loop de GO

em go não temos o WHILE TRUE , a referencia parecida para fazer um loop infinito em go seria 

```go
  for {
    // EM ALGUM MOMENTO PODERIA DAR UM BREAK
    break
  }
```

em resumo é 

```go
  for condition {
    // code
  }
```

existem algumas maneira de fazer o for 


Formas do `For`

```go
  i := 0
  for i >= 10 {
    // code
    i += 1
  }

  for i := 0; i>= 10 {
    // code
    i += 1
  }

  for i := 0; i>= 10; i++ {
    // code
  }
```


E tmb temos o `For Range`

```go
  for i := range 3 {
    // code
  }

  var arr [2]string{"ALO", "ALE"}

  for i, elem := range arr {
    // i - index = 0
    // elem - elemento = "ALO
  }

  // se não quisermos o index podemos colocar _ para ignorar ele

  for _, elem := range arr {
    // code
  }

  // ja se não queremos o elem usamos somente o i { ou qualquer nome para a var kk }

  for i := range arr {
    // code
  }
```


Temos também o continue que faz o loop continuar para a proxima iteração

```go
  for n := range 6 {
    if n%2 == 0 {
      // Caso entre aqui o print nao rodara para aquele index pois o continue passa para o proximo.
      continue
    }
    fmt.Println(n)
  }
```