# Analisador Léxico - a primeira fase da Vanguarda

# Gustavo Lopes Rodrigues

## O que você vai ver?

- O que é um Analisador Léxico
- Como funciona o Analisador Léxico

## Pré-requisitos 

- Introdução
- Tabela de Símbolos

## Definição

Um analisador léxico, também conhecido como lexer ou tokenizador, é um programa que recebe entrada na forma de um fluxo de caracteres e o divide em tokens. Esses tokens são normalmente substrings da entrada que são separados por algum tipo de delimitador, como espaço em branco ou pontuação.

O analisador léxico funciona lendo a entrada caractere por caractere e agrupando-os em tokens com base em padrões definidos por um conjunto de regras chamadas regras lexicais ou definições lexicais. Essas regras especificam os padrões que o lexer deve procurar na entrada, como palavras-chave, identificadores e pontuação.

Vamos considerar a seguinte entrada como um exemplo:
```x
x = 3 + 4;
``` 
Um lexer para esta entrada, por exemplo, pode reconhecer os seguintes tokens:
```x
Tipo - Identificador; Lexema -"x"
Tipo - Operador; Lexema - "="
Tipo - Literal; Lexema - "3"
Tipo - Operador; Lexema - "+"
Tipo - Literal; Lexema - "4"
Tipo - Pontuação; Lexema - ";"
``` 
O lexer leria a entrada caractere por caractere e os agruparia em tokens com base nas regras lexicais que foram definidas. Nesse caso, as regras podem especificar que os identificadores consistem em uma letra seguida por zero ou mais letras ou dígitos, os literais são sequências de dígitos e os operadores são determinados caracteres especiais, como '+' e '='.

Uma vez que a entrada tenha sido dividida em tokens, ela pode ser passada para outras partes do compilador ou interpretador, como o analisador sintático, que usará os tokens para construir uma árvore sintática ou realizar outras operações.

# Línks úteis

- [Compilador para humanos - Análise Léxica](https://johnidm.gitbooks.io/compiladores-para-humanos/content/part1/lexical-analysis.html)
- [Aula 06 - Análise Léxica - Judson Santiago](https://youtu.be/gzY-CTY4msg)
