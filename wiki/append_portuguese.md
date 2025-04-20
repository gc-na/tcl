<!--
Meta Description: # Append: Comando Tcl para Concatenar Strings e Listas ## Sinopse O comando `append` em Tcl é utilizado para concatenar strings ou adicionar elementos...
Meta Keywords: append, tcl, strings, variável, que
-->

# Append: Comando Tcl para Concatenar Strings e Listas

## Sinopse
O comando `append` em Tcl é utilizado para concatenar strings ou adicionar elementos a variáveis, permitindo a manipulação eficiente de dados em formato textual e listas.

## Documentação
O comando `append` serve para agregar dados a uma variável existente. É comum em operações que exigem a construção dinâmica de strings ou listas. A sintaxe básica do comando é:

```tcl
append variable ?value1 value2 ...?
```

### Propósito
O principal objetivo do `append` é facilitar a adição de conteúdo a uma variável, evitando a necessidade de reatribuição ou criação de novas variáveis.

### Uso
- **Variável**: O nome da variável à qual o conteúdo será adicionado. Se a variável não existir, ela será criada.
- **Value(s)**: Um ou mais valores que serão concatenados à variável.

### Detalhes
- O `append` pode ser utilizado com múltiplos valores, que serão concatenados na ordem em que são passados.
- Se a variável já contém algum valor, o novo conteúdo será adicionado ao final do valor existente.
- O comando é especialmente útil ao trabalhar com loops ou quando a construção de strings complexas é necessária.

## Exemplos
### Exemplo 1: Concatenando Strings
```tcl
set texto "Olá"
append texto ", mundo!"
puts $texto  ;# Saída: Olá, mundo!
```

### Exemplo 2: Adicionando Múltiplos Valores
```tcl
set lista ""
append lista 1 2 3 4
puts $lista  ;# Saída: 1234
```

### Exemplo 3: Usando com Variáveis
```tcl
set nome "João"
set sobrenome "Silva"
append nome " " $sobrenome
puts $nome  ;# Saída: João Silva
```

## Explicação
Ao usar o comando `append`, é importante estar ciente de algumas peculiaridades:

- **Espaços**: Se for necessário adicionar espaços ou outros separadores, eles devem ser incluídos explicitamente nos valores.
- **Tipo de Dados**: O `append` converte automaticamente números em strings, mas é sempre bom garantir que os valores que você está concatenando sejam do tipo esperado para evitar comportamentos inesperados.
- **Performance**: Em operações de concatenação em loop, o `append` é geralmente mais eficiente do que a reatribuição contínua de variáveis.

## Resumo em Uma Linha
O `append` em Tcl permite a concatenação eficiente de strings e listas, facilitando a manipulação de dados.