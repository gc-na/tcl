<!--
Meta Description: # lmap: Comando Tcl para Manipulação de Listas ## Sinopse O comando `lmap` em Tcl é uma ferramenta poderosa para iterar sobre listas, permitindo a apl...
Meta Keywords: lista, uma, lmap, listas, comando
-->

# lmap: Comando Tcl para Manipulação de Listas

## Sinopse
O comando `lmap` em Tcl é uma ferramenta poderosa para iterar sobre listas, permitindo a aplicação de uma operação a cada elemento, resultando em uma nova lista. É especialmente útil para transformações de dados em listas de forma concisa e legível.

## Documentação
### Propósito
O `lmap` é utilizado para aplicar uma função a cada elemento de uma lista, gerando uma nova lista com os resultados da aplicação dessa função. Ele combina a simplicidade de iteração com a elegância da manipulação de listas, permitindo que os desenvolvedores Tcl escrevam código mais limpo e eficiente.

### Uso
A sintaxe básica do `lmap` é a seguinte:

```tcl
lmap var lista ?var2 lista2? { comando }
```

- `var`: Variável que irá armazenar cada elemento da lista durante a iteração.
- `lista`: A lista a ser iterada.
- `var2`: Opcional. Uma segunda variável para listas adicionais.
- `lista2`: Opcional. Uma segunda lista a ser iterada simultaneamente.
- `comando`: O bloco de código que será executado para cada elemento da lista.

O resultado é uma nova lista composta pelos resultados da execução do comando.

### Detalhes
- O `lmap` pode lidar com múltiplas listas, utilizando variáveis adicionais para cada lista.
- Se as listas não forem do mesmo tamanho, `lmap` irá iterar até a menor lista ser completamente percorrida.
- O bloco de código (comando) pode incluir qualquer operação válida em Tcl, incluindo chamadas a outras funções.

## Exemplos
### Exemplo 1: Quadrados de uma lista de números
```tcl
set numeros {1 2 3 4 5}
set quadrados [lmap n $numeros {expr {$n * $n}}]
puts $quadrados  ;# Saída: {1 4 9 16 25}
```

### Exemplo 2: Concatenando duas listas
```tcl
set lista1 {a b c}
set lista2 {1 2 3}
set concatenados [lmap {x y} $lista1 $lista2 {concat $x $y}]
puts $concatenados  ;# Saída: {a1 b2 c3}
```

## Explicação
Uma armadilha comum ao usar `lmap` é esquecer que o bloco de comando deve retornar um valor. Se o bloco não retornar nada, a lista resultante será vazia. Além disso, ao manipular múltiplas listas, é importante garantir que todas tenham o mesmo comprimento para evitar resultados inesperados. Ao trabalhar com listas grandes, considere o desempenho, pois o `lmap` pode consumir mais recursos dependendo da complexidade do comando aplicado.

## Resumo em uma linha
O `lmap` em Tcl permite aplicar operações em cada elemento de uma lista, gerando uma nova lista de forma concisa e eficiente.