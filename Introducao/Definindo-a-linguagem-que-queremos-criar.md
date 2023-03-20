# Definindo a linguagem que queremos criar

Nesta aula iremos definir a linguagem que iremos criar. Ela é mais simples do que a maior parte das linguagens 
imperativas que utilizamos hoje em dia, mas será o suficiente para entendermos os conceitos que queremos aprender na disciplina.

## Linguagem Pyxer

A linguagem "Pyxer" é uma linguagem imperativa simplificada que oferece tratamento para 5 tipos básicos: char, string, int, float, boolean. A sintaxe da linguagem Pyxer é inspirada na linguagem Python, tornando-a mais fácil de ler e escrever.

Os tipos básicos são os seguintes:

 - char: um escalar que varia de 0 a 255, podendo ser escrito em formato alfanumérico ou hexadecimal.
 - string: uma sequência de no máximo 255 caracteres úteis, terminada pelo byte 0 em memória. Constantes string são delimitadas por aspas simples ou duplas e não devem conter aspas ou quebra de linha.
 - int: um escalar que varia de -2^31 a 2^31 - 1.
 - float: um número decimal com 6 casas de precisão, sem notação científica, variando de -99999.9 a 99999.9. A precisão é compartilhada entre a parte inteira e a fracionária.
 - boolean: representa os valores lógicos verdadeiro e falso, expressos como True e False.
 - Os identificadores de constantes e variáveis são compostos de letras, dígitos e sublinhados, devem começar com letra ou sublinhado e ter no máximo 32 caracteres. Maiúsculas e minúsculas não são diferenciadas.

### Estrutura de um programa Pyxer

Um programa em Pyxer consiste em declarações e comandos, sem a necessidade de terminar as linhas com ponto-e-vírgula. A estrutura básica de um programa-fonte é da seguinte forma:

```
(Declarações ∪ Comandos)*  fim_arquivo 
```
Declarações e comandos não precisam ser finalizados por ponto-e-vírgula. Um bloco de comandos pode substituir um comando. Nesse caso, o bloco é iniciado por : e indentado, contendo uma sequência de 0 ou mais comandos. Dentro de um bloco de comandos, não pode haver declarações.

### Declarações e Comandos
A seguir, é feita a descrição informal da sintaxe das declarações e comandos da linguagem Pyxer:

 - Declaração de variáveis: é da forma tipo nome_variavel, onde tipo pode ser int, float, string, boolean, ou char e nome_variavel é um identificador. As variáveis podem ser opcionalmente inicializadas na forma nome_variavel = valor.

 - Declaração de constantes: é da forma const nome_constante = valor, onde nome_constante é um identificador e valor é uma constante numérica, string, boolean, hexadecimal ou caractere alfanumérico.

 - Comando de atribuição: é da forma variavel = expressao para tipos numéricos, lógico, caractere e string ou variavel[indice] = expressao para elementos de strings (caracteres).

Comando de repetição pode assumir duas formas:

```
while expressao:
    comando
```
onde expressao é do tipo lógico. A repetição dos comandos será feita enquanto a expressão for verdadeira.

### Comando de teste: 

Pode assumir as seguintes formas, onde expressao é do tipo lógico:

```
if expressao:
    comando1
elif expressao:
    comando2
else:
    comando3
```

Os comandos elif e else são opcionais. Eles permitem criar múltiplos testes condicionais ou uma ação padrão caso todas as condições anteriores falhem.

 - Comando nulo: Um pass indica um comando nulo. Nada é executado nesse comando.

 - Comando de leitura: é da forma variavel = input(), onde variavel é um identificador de variável numérica, caractere alfanumérico ou string. A função input() pode receber uma string como parâmetro para exibir uma mensagem antes da leitura.

 - Comandos de escrita: são da forma print(expressao1, expressao2, ...) onde as expressões são valores numéricos, caracteres ou strings. A função print() imprime os valores separados por espaços e, por padrão, adiciona uma quebra de linha após a impressão.

Eis aqui um exemplo de um programa escrito na linguagem Pyxer:

```
nome = input("Digite seu nome: ")

float percentual
int i = 1
const N = 10
while i <= N:
    percentual = float(i) / N
    print(f"{percentual:.6f}: Olá, {nome}")
    i = i + 1
```

Este programa solicita ao usuário seu nome e imprime uma mensagem de saudação com um percentual crescente 10 vezes.




