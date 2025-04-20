<!--
Meta Description: # lindex: Acesso a Elementos em Listas no Tcl ## Sinopse O comando `lindex` no Tcl é utilizado para acessar elementos individuais em listas, permitind...
Meta Keywords: lista, lindex, uma, elemento, índice
-->

# lindex: Acesso a Elementos em Listas no Tcl

## Sinopse
O comando `lindex` no Tcl é utilizado para acessar elementos individuais em listas, permitindo a recuperação de valores específicos de uma lista de forma eficiente.

## Documentação
O `lindex` é uma função fundamental no Tcl, projetada para trabalhar com listas. Sua principal finalidade é extrair um elemento de uma lista com base em um índice fornecido. A sintaxe básica é:

```tcl
lindex lista índice
```

### Parâmetros:
- **lista**: A lista da qual o elemento será extraído. Pode ser uma lista literal, uma variável que contém uma lista ou a saída de um comando que gera uma lista.
- **índice**: O índice do elemento que você deseja recuperar. No Tcl, os índices começam em 0, ou seja, o primeiro elemento de uma lista é acessado usando o índice 0.

### Retorno:
O `lindex` retorna o elemento que corresponde ao índice fornecido. Se o índice estiver fora do intervalo da lista, o comando retornará uma string vazia.

## Exemplos

### Exemplo 1: Acesso a um Elemento Simples
```tcl
set minhaLista {maçã banana cereja}
set fruta [lindex minhaLista 1]
puts $fruta  ;# Saída: banana
```

### Exemplo 2: Acesso a um Elemento em uma Lista Aninhada
```tcl
set listaAninhada { {a b c} {d e f} {g h i} }
set elemento [lindex [lindex listaAninhada 1] 2]
puts $elemento  ;# Saída: f
```

### Exemplo 3: Tentativa de Acesso a um Índice Inválido
```tcl
set lista {1 2 3}
set invalido [lindex lista 5]
puts $invalido  ;# Saída: (string vazia)
```

## Explicação
Um erro comum ao usar `lindex` é tentar acessar um índice que não existe na lista, resultando em uma string vazia. É importante sempre verificar o tamanho da lista com `llength` antes de tentar acessar um elemento para evitar esse problema.

Outro ponto a ser notado é que `lindex` pode ser usado em listas aninhadas, mas o acesso a elementos aninhados requer múltiplas chamadas a `lindex`, como demonstrado no exemplo 2.

## Resumo em Uma Linha
O comando `lindex` no Tcl é utilizado para acessar elementos individuais em listas, retornando o valor correspondente ao índice especificado.