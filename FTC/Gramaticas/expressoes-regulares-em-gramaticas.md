# Expressões regulares juntos as gramáticas

## Você vai aprender
- Como unir conceitos de gramáticas e expressões regulares

## Pré-requisitos
- Conhecimento de gramáticas
- Conhecimento de expressões regulares

## Criando gramáticas mais complexas

As expressões regulares são padrões de busca que descrevem um conjunto de strings. Elas são frequentemente usadas em programas para buscar 
por padrões em textos ou em compiladores para reconhecer padrões de entrada. As gramáticas, por sua vez, são conjuntos de regras que definem 
uma linguagem formal. Elas são utilizadas em compiladores para analisar e transformar o código fonte de um programa em uma representação 
intermediária ou código objeto.

No contexto dos Fundamentos Teóricos de Computação e Compiladores, é comum utilizar expressões regulares em conjunto com gramáticas para 
definir as regras de análise léxica de um compilador. A análise léxica é a primeira etapa do processo de compilação, na qual o código fonte 
é analisado para identificar os tokens (símbolos básicos) que o compõem.

Para definir as regras de análise léxica de um compilador, é necessário especificar os padrões que cada token pode ter. Esses padrões 
são geralmente descritos por meio de expressões regulares. Por exemplo, se quisermos identificar números inteiros em um código fonte, 
podemos definir uma expressão regular que descreva o padrão de um ou mais dígitos: [0-9]+.

Em seguida, esses padrões são combinados com as regras gramaticais do compilador para definir como cada token é formado. Por exemplo, 
se quisermos definir que um token que começa com uma letra seguida de zero ou mais letras ou dígitos é um identificador, podemos usar 
a seguinte regra gramatical:

``` 
IDENTIFICADOR → letra (letra | digito)*
```
Nessa regra, **letra** e **digito** são símbolos terminais que representam expressões regulares para letras e dígitos, respectivamente. 
A expressão (letra | digito)* indica que o identificador pode ter zero ou mais letras ou dígitos após a primeira letra.

Assim, as expressões regulares são uma ferramenta útil para definir padrões de busca em textos e para especificar os padrões de tokens 
em um compilador. Quando combinadas com as gramáticas, elas permitem especificar as regras de análise léxica de um compilador de forma clara e concisa.
