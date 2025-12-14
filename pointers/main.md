# 13 Pointers

Go suporta ponteiros, permitindo que você passe referências a valores e registros dentro do seu programa.

Vamos mostrar como os ponteiros funcionam em contraste com os valores usando duas funções: `zeroval` e `zeroptr`. `zeroval` recebe um parâmetro `int`, portanto, os argumentos são passados para ela por valor. `zeroval` receberá uma cópia de `ival` distinta daquela presente na função que a chamou.

`zeroptr`, por outro lado, recebe um parâmetro `*int`, o que significa que ela aceita um ponteiro para um inteiro. O código `*iptr` no corpo da função então desreferencia o ponteiro do seu endereço de memória para o valor atual nesse endereço. Atribuir um valor a um ponteiro desreferenciado altera o valor no endereço referenciado.

A sintaxe `&i` retorna o endereço de memória de `i`, ou seja, um ponteiro para `i`.

Ponteiros também podem ser impressos.

`zeroval` não altera o valor de `i` na função `main`, mas `zeroptr` sim, pois possui uma referência ao endereço de memória daquela variável.

```go
  package main

  import "fmt"

  func zeroval(ival int) {
      ival = 0
  }

  func zeroptr(iptr *int) {
      *iptr = 0
  }

  func main() {
      i := 1
      fmt.Println("initial:", i)

      zeroval(i)
      fmt.Println("zeroval:", i)

      zeroptr(&i)
      fmt.Println("zeroptr:", i)

      fmt.Println("pointer:", &i)
  }
```