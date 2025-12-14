## 12 Range over Built-in Types

A função `range` itera sobre elementos em diversas estruturas de dados predefinidas. Vamos ver como usar `range` com algumas das estruturas de dados que já aprendemos.

Aqui usamos o operador range para somar os números em uma fatia. Os arrays também funcionam dessa maneira.

A função `range` em arrays e slices fornece tanto o índice quanto o valor de cada entrada. Acima, não precisávamos do índice, então o ignoramos com o identificador vazio `_`. Às vezes, porém, precisamos dos índices.

O operador `range` em um mapa itera sobre pares chave/valor.

O operador `range` também pode iterar apenas sobre as chaves de um mapa.

A função `range` em strings itera sobre os pontos de código Unicode. O primeiro valor é o índice do byte inicial da runa e o segundo é a própria runa. Consulte Strings e Runas para obter mais detalhes.

```go
  package main

  import "fmt"

  func main() {

      nums := []int{2, 3, 4}
      sum := 0
      for _, num := range nums {
          sum += num
      }
      fmt.Println("sum:", sum)

      for i, num := range nums {
          if num == 3 {
              fmt.Println("index:", i)
          }
      }

      kvs := map[string]string{"a": "apple", "b": "banana"}
      for k, v := range kvs {
          fmt.Printf("%s -> %s\n", k, v)
      }

      for k := range kvs {
          fmt.Println("key:", k)
      }

      for i, c := range "go" {
          fmt.Println(i, c)
      }
  }
```

$ go run range-over-built-in-types.go
sum: 9
index: 1
a -> apple
b -> banana
key: a
key: b
0 103
1 111