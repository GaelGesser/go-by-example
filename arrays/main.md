## 8 - Arrays

Arrays em Go tem algumas particularidades, em primeiro lugar os arrays sempre vão precisar receber um tamanho

```go
  var a [5]int  
```

dessa maneira a cima que declaramos um array, outro detalhe que se não passamos os valores o ele vai criar o array como 0 em todos os index exp de saída 
`[0 0 0 0 0]`

para inicializarmos ja com valores ou passando um index especifico fazemos assim

```go
  var nomes [10]string{"Gabriel", 5: "Eduarda"}
```

para passar algum valor a um array e buscar ele fazemos dessa maneira

```go
  var a [2]int

  a[1] = 100

  // resultado = [100, 0]

  fmt.Println(a[1])

  // 100
```

temos tmb o `len()` que retorna o tamanho do array 

podemos tmb para setar um array e deixa o compilador verificar o tamanho podemos fazer assim

```go
  b := [...]int{1,2,3,4,5,6,7,9}
```