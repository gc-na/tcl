<!--
Meta Description: # regsub: Substituição de Expressões Regulares em Tcl ## Sinopse O comando `regsub` em Tcl é utilizado para realizar substituições em strings com base...
Meta Keywords: regsub, substituição, tcl, string, set
-->

# regsub: Substituição de Expressões Regulares em Tcl

## Sinopse
O comando `regsub` em Tcl é utilizado para realizar substituições em strings com base em padrões de expressões regulares, permitindo transformar texto de maneira flexível e poderosa.

## Documentação
O `regsub` é uma ferramenta fundamental para manipulação de strings em Tcl, que permite substituir partes de uma string que correspondem a uma expressão regular específica. A sintaxe básica do comando é:

```tcl
regsub ?opções? expressão string substituição ?variável?
```

### Parâmetros:
- **opções**: (opcional) Argumentos adicionais para modificar o comportamento, como `-all` para substituir todas as ocorrências.
- **expressão**: A expressão regular que será usada para encontrar padrões na string.
- **string**: A string original onde a substituição será realizada.
- **substituição**: O texto que substituirá as partes correspondentes da string original.
- **variável**: (opcional) Se especificada, a string resultante da substituição será armazenada nesta variável.

### Exemplo de Uso:
Aqui está um exemplo básico de como usar o `regsub`:

```tcl
set texto "O céu é azul e o sol é amarelo."
set novoTexto [regsub {azul} $texto "verde"]
puts $novoTexto
```
Saída:
```
O céu é verde e o sol é amarelo.
```

## Exemplos
1. **Substituição Simples**:
   ```tcl
   set frase "A maçã é vermelha."
   set novaFrase [regsub {vermelha} $frase "verde"]
   puts $novaFrase  ; # Saída: A maçã é verde.
   ```

2. **Substituição de Todas as Ocorrências**:
   ```tcl
   set texto "O gato e o rato são animais."
   set novoTexto [regsub -all {o} $texto "a"]
   puts $novoTexto  ; # Saída: A gato e a rato são animais.
   ```

3. **Substituição com Grupos**:
   ```tcl
   set data "2023-10-01"
   set novaData [regsub {(\d{4})-(\d{2})-(\d{2})} $data {\2/\3/\1}]
   puts $novaData  ; # Saída: 10/01/2023
   ```

## Explicação
- **Diferença entre regsub e regsub -all**: O `regsub` padrão substitui apenas a primeira ocorrência do padrão. Para substituir todas as ocorrências, use a opção `-all`.
  
- **Cuidado com os padrões**: Ao usar expressões regulares, é importante entender como elas funcionam, pois padrões mal definidos podem não gerar os resultados esperados.

- **Referência a Grupos**: Na string de substituição, você pode referenciar grupos capturados usando `\1`, `\2`, etc., onde o número representa a posição do grupo na expressão regular.

## Resumo em Uma Linha
O `regsub` em Tcl permite substituir partes de uma string com base em padrões de expressões regulares, facilitando a manipulação avançada de texto.