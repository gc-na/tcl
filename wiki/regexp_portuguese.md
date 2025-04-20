<!--
Meta Description: # regexp: Expresse e Manipule Strings com Expressões Regulares em Tcl ## Sinopse O comando `regexp` em Tcl permite a utilização de expressões regulare...
Meta Keywords: tcl, regexp, que, texto, expressões
-->

# regexp: Expresse e Manipule Strings com Expressões Regulares em Tcl

## Sinopse
O comando `regexp` em Tcl permite a utilização de expressões regulares para pesquisar, verificar e manipular cadeias de caracteres, oferecendo uma maneira poderosa e flexível de trabalhar com dados textuais.

## Documentação
O comando `regexp` é utilizado para realizar correspondências de padrões em strings utilizando expressões regulares. A sintaxe básica do comando é a seguinte:

```tcl
regexp ?opções? padrão string ?matchVar? ?submatchVar1? ?submatchVar2? ... ?submatchVarN?
```

### Parâmetros:
- **opções**: Parâmetros opcionais que alteram o comportamento da correspondência (como `-nocase` para ignorar diferenças entre maiúsculas e minúsculas).
- **padrão**: A expressão regular que será utilizada para a correspondência.
- **string**: A string que será analisada em busca do padrão.
- **matchVar**: (opcional) Uma variável onde será armazenado o texto que corresponde ao padrão.
- **submatchVar**: (opcional) Variáveis que armazenarão as partes da string que correspondem a subgrupos definidos na expressão regular.

### Retorno:
O comando retorna `1` se houver uma correspondência e `0` caso contrário. Se `matchVar` for especificado, a variável será preenchida com a correspondente à expressão regular encontrada.

## Exemplos

### Exemplo 1: Correspondência Simples
```tcl
set texto "O gato está no telhado."
if {[regexp {gato} $texto]} {
    puts "O padrão foi encontrado!"
}
```

### Exemplo 2: Usando Subgrupos
```tcl
set texto "Contato: 123-456-7890"
if {[regexp {(\d+)-(\d+)-(\d+)} $texto match parte1 parte2 parte3]} {
    puts "Código: $parte1, Número: $parte2, Sufixo: $parte3"
}
```

### Exemplo 3: Ignorando Maiúsculas
```tcl
set texto "Tcl é incrível!"
if {[regexp {-nocase {tcl}} $texto]} {
    puts "O padrão foi encontrado, ignorando maiúsculas!"
}
```

## Explicação
O uso de expressões regulares pode parecer complicado no início. Um dos principais desafios é o entendimento da sintaxe das expressões. Além disso, a definição correta dos subgrupos pode levar a confusões se não for feita de forma cuidadosa. É importante também lembrar que o uso de opções, como `-nocase`, pode alterar substancialmente o resultado da correspondência. Sempre teste seus padrões com diferentes entradas para garantir que estão funcionando como esperado.

## Resumo em Uma Linha
O comando `regexp` em Tcl permite realizar buscas e manipulações de strings utilizando expressões regulares de forma eficiente e flexível.