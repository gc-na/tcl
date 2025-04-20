<!--
Meta Description: # lrange: Comando Tcl para Manipulação de Listas ## Sinopse O comando `lrange` em Tcl é utilizado para extrair um subconjunto de elementos de uma list...
Meta Keywords: lista, lrange, uma, tcl, índice
-->

# lrange: Comando Tcl para Manipulação de Listas

## Sinopse
O comando `lrange` em Tcl é utilizado para extrair um subconjunto de elementos de uma lista, permitindo manipulações eficientes de dados em forma de listas.

## Documentação
O `lrange` é uma função fundamental da biblioteca Tcl que permite ao usuário obter uma sub-lista a partir de uma lista existente. A sintaxe do comando é a seguinte:

```tcl
lrange lista início fim
```

### Parâmetros:
- **lista**: A lista de onde os elementos serão extraídos.
- **início**: O índice inicial (zero baseado) da sub-lista que se deseja obter. O índice pode ser negativo, onde -1 representa o último elemento da lista.
- **fim**: O índice final (zero baseado) da sub-lista. Assim como o início, o índice pode ser negativo.

### Detalhes:
- O comando retorna todos os elementos da lista do índice `início` ao índice `fim`, inclusive.
- Se `início` for maior do que `fim`, o comando retornará uma lista vazia.
- Caso `fim` seja omitido, todos os elementos a partir de `início` até o final da lista serão retornados.

## Exemplos

### Exemplo 1: Extraindo uma Sub-lista
```tcl
set minhaLista {a b c d e f}
set subLista [lrange minhaLista 1 3]
# Resultado: {b c d}
```

### Exemplo 2: Usando Índices Negativos
```tcl
set minhaLista {a b c d e f}
set subLista [lrange minhaLista -3 -1]
# Resultado: {d e f}
```

### Exemplo 3: Extraindo até o Final
```tcl
set minhaLista {1 2 3 4 5}
set subLista [lrange minhaLista 2]
# Resultado: {3 4 5}
```

### Exemplo 4: Índice Invertido
```tcl
set minhaLista {x y z}
set subLista [lrange minhaLista 2 1]
# Resultado: {}
```

## Explicação
Um erro comum ao usar `lrange` é confundir os índices. Lembre-se de que o índice `início` deve ser menor ou igual ao índice `fim` para retornar uma sub-lista não vazia. Além disso, a manipulação de índices negativos pode ser confusa para iniciantes. É importante sempre verificar se os índices estão dentro dos limites da lista para evitar resultados inesperados.

Outra armadilha é esquecer que `lrange` não altera a lista original; ele apenas retorna uma nova lista baseada nos índices fornecidos. Caso você precise alterar a lista original, considere usar outros comandos como `lreplace`.

## Resumo em Uma Linha
O comando `lrange` em Tcl permite extrair sub-listas de uma lista existente, facilitando a manipulação de dados listados.