<!--
Meta Description: # Comando foreach no Tcl: Iteração Eficiente em Listas ## Sinopse O comando `foreach` no Tcl é utilizado para iterar sobre listas, permitindo a execuç...
Meta Keywords: foreach, iteração, listas, tcl, lista
-->

# Comando foreach no Tcl: Iteração Eficiente em Listas

## Sinopse
O comando `foreach` no Tcl é utilizado para iterar sobre listas, permitindo a execução de um bloco de código para cada elemento ou conjunto de elementos. É uma ferramenta poderosa para manipular dados de maneira simples e eficiente.

## Documentação
O comando `foreach` tem como propósito principal facilitar a iteração sobre listas, seja para processar elementos individuais ou pares de elementos. A sintaxe básica do comando é a seguinte:

```tcl
foreach variável lista {
    # bloco de código
}
```

### Parâmetros:
- **variável**: Um ou mais nomes de variáveis que receberão os valores da lista a cada iteração.
- **lista**: Uma lista de elementos sobre a qual a iteração será realizada.

### Uso:
O `foreach` pode ser utilizado de duas maneiras:
1. **Iteração Simples**: Para percorrer uma única lista.
2. **Iteração em Múltiplas Listas**: Para percorrer várias listas simultaneamente, onde cada variável receberá um elemento correspondente de cada lista.

#### Exemplo de Iteração Simples:
```tcl
set lista {1 2 3 4 5}
foreach número $lista {
    puts "Número: $número"
}
```

#### Exemplo de Iteração em Múltiplas Listas:
```tcl
set nomes {Alice Bob Carol}
set idades {25 30 22}
foreach nome idade [list $nomes $idades] {
    puts "$nome tem $idade anos."
}
```

## Exemplos
### Exemplo 1: Iteração Simples
```tcl
set frutas {maçã banana laranja}
foreach fruta $frutas {
    puts "Fruta: $fruta"
}
```

### Exemplo 2: Iteração com Múltiplas Listas
```tcl
set cidades {São Paulo Rio de Janeiro Brasília}
set populações {12M 6M 3M}
foreach cidade população [list $cidades $populações] {
    puts "A cidade $cidade tem uma população de $população habitantes."
}
```

## Explicação
Um dos principais desafios ao usar `foreach` é garantir que as listas a serem iteradas tenham o mesmo tamanho quando se utiliza a iteração em múltiplas listas. Caso contrário, o Tcl irá parar na menor lista, o que pode levar a resultados inesperados. Além disso, é importante lembrar que o escopo das variáveis definidas no `foreach` é limitado ao bloco de código, portanto, elas não estarão acessíveis fora dele.

### Dicas:
- Use `foreach` quando precisar de uma maneira clara e concisa para iterar sobre coleções.
- Verifique se as listas têm o mesmo comprimento ao usar múltiplas listas para evitar erros de iteração.

## Resumo em Uma Linha
O comando `foreach` no Tcl permite iterar eficientemente sobre listas, facilitando a execução de operações em cada elemento.