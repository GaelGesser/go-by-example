## 9 - Slices

Slices são importantes em Go, eles oferecem uma interface melhor para sequência do que arrays.

slices são tipados apenas telo tipo dos elementos que contêm

um slice não inicializado é igual a nil e tem comprimento 0 exp:

```go
  var s []string
  fmt.Println("uninit:", s, s == nil, len(s) == 0)

  // uninit: [] true true

```
Para criar um slice com comprimeto diferente de zero, use a função `make`.

```go
  s = make([]string, 3)
  fmt.Println("emp:", s, "len:", len(s), "cap:", cap(s))

  // emp: [ ] len:3 cap:3
```

Por padrão, a capacidade de um slice novo é igual ao seu comprimento, se por alguma razão soubermos que ele ira crescer podemos passar um terceiro argumento para definir a capacidade

```go
make([]string, 3 , 6)
```

Para acessar os slices podemos fazer da mesma maneira que os arrays segue exp

```go
  s := make([]string, 3)

  s[0]
  s[1]
  s[2]
```

temos o `len()` que retorna o comprimento do slice

Os slices alem das operações básicas , possuem recursos que os tornam mais ricos que arrays:

`append:` função que adiciona um ou mais valores a um slice e retorna o slice resultante
IMPORTANTE: append pode retornar um novo slice ( se a capacidade precisar aumentar ) então sempre precisamos usar o valor retornado exp

```go
  s := make([]string, 3)
  v := "gabriel"
  s = append(s, v)

  // Outro detalhe é que o append adiciona ao fim do slice
  // como vemos a saída aqui será 

  // [    gabriel]
```
`copy:` literalmente oq o proprio nome diz , copiar um slice para o outro, ex:

```go
  s := make([]string, 3)

  s[0] = "1"
  s[1] = "2"
  s[2] = "3"

  c := make([]string, len(s))
	copy(c, s)
	fmt.Println("c:", c)

  // resultado : s: [1 2 3]
  // resultado : c: [1 2 3]
```

E por ultimo temos o slice

`slice[low:high]:` segue exemplos

```go
  l := s[2:5]
	fmt.Println("sl1:", l)

	l = s[:5]
	fmt.Println("sl2:", l)

	l = s[2:]
	fmt.Println("sl3:", l)
```

temos tambem, o `Equal()` segue exp:

```go
	t := []string{"g", "h", "i"}
	fmt.Println("dcl:", t)
  
  t2 := []string{"g", "h", "i"}
  if slices.Equal(t, t2) {
    fmt.Println("t == t2")
  }
```

Slices podem ser compostos em estruturas de dados multidimensionais (por exemplo, [][]int). A diferença em relação a arrays multidimensionais é que os slices internos podem ter comprimentos diferentes (jagged slices), ou seja, cada linha pode ter tamanho diferente.