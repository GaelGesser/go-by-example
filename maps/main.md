## 10 - MAPS

Maps são tipo de dados associativo embutido em Go

Para criar um map vazio, usamos a função `make():`

```go

  m := make(map[tipo-da-chave]tipo-do-valor)

``` 

para obter o valor de uma chave usamos 

nome[chave]

se a chave não existir , o valor zero do tipo do valor é retornado

---

Se imprimirmos um map , ele ira mostrar chave/valor 

Usando o `len()` em um map ele retorna o número de key/value que existem no map

Função `delete()` remove uma key/value no map

para remover todas keys/values usamos `clear()`

---

Temos uma segunda opção de retorno , essa opção retorna se a key existe no map

```go

  c := map[string]string{"nome": "gabriel"}

  valueKey, existKey := c["sobrenome"]
  fmt.Println("Valor da key: ", valueKey)
  fmt.Println("Existe a key? : ", existKey)

```

para iniciar um map em uma linha podemos usar assim 

```go
  c := map[string]string{"nome": "gabriel"}
```

o retorno de print do map é 

`map[k:v k:v]`