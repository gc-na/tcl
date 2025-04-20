<!--
Meta Description: # Comando "scan" em Tcl: Análise e Extração de Dados ## Sinopse O comando `scan` em Tcl é utilizado para analisar strings e extrair dados formatados a...
Meta Keywords: string, scan, formato, comando, para
-->

# Comando "scan" em Tcl: Análise e Extração de Dados

## Sinopse
O comando `scan` em Tcl é utilizado para analisar strings e extrair dados formatados a partir delas, permitindo que você converta partes de uma string em variáveis específicas.

## Documentação
O comando `scan` tem a seguinte sintaxe:

```tcl
scan string format var1 var2 ...
```

### Propósito
Essa função é útil para ler dados de strings que seguem um formato específico, extraindo valores para variáveis individuais.

### Uso
- **string**: A string que será analisada.
- **format**: Uma string de formato que especifica como os dados devem ser lidos. Os especificadores de formato podem incluir `%d` para inteiros, `%f` para floats, `%s` para strings, entre outros.
- **var1, var2, ...**: Variáveis onde os resultados da análise serão armazenados.

### Detalhes
O comando `scan` retorna o número de itens que foram extraídos com sucesso. Se a string não corresponder ao formato fornecido, o retorno será menor que o número de variáveis fornecidas. Este comando é sensível a espaços em branco e caracteres especiais, portanto, é importante garantir que o formato corresponda exatamente à string.

## Exemplos

### Exemplo 1: Extraindo Inteiros
```tcl
set data "10 20"
set result [scan $data "%d %d" a b]
puts "Números extraídos: $a, $b (itens lidos: $result)"
```
**Saída:**
```
Números extraídos: 10, 20 (itens lidos: 2)
```

### Exemplo 2: Lendo um Float e uma String
```tcl
set info "3.14 pi"
set result [scan $info "%f %s" number name]
puts "Número: $number, Nome: $name (itens lidos: $result)"
```
**Saída:**
```
Número: 3.14, Nome: pi (itens lidos: 2)
```

### Exemplo 3: Formato Incorreto
```tcl
set data "10 apples"
set result [scan $data "%d %d" num fruit]
puts "Itens lidos: $result"
```
**Saída:**
```
Itens lidos: 1
```
Neste caso, `fruit` não recebeu um valor, pois o formato especificado não corresponde à string.

## Explicação
Um erro comum ao usar o `scan` é não alinhar o formato com a string de entrada. Por exemplo, se a string contém caracteres extras ou espaços, o comando pode não funcionar como esperado. Sempre verifique se a string segue o formato definido. Além disso, esteja atento ao retorno do comando, pois ele pode indicar quantos itens foram efetivamente lidos, o que pode ser útil para depuração.

## Resumo em Uma Linha
O comando `scan` em Tcl permite analisar strings e extrair dados formatados, armazenando-os em variáveis para uso posterior.