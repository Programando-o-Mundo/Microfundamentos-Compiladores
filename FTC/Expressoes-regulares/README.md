# Expressões regulares

## Você vai aprender

* O que são Expressões regulares
* Alguns exemplos
* Como são utilizadas

## Pré-requisitos

* Nenhum

## Definição

Nesta aula, vamos falar sobre expressões regulares, que são padrões de texto que definem um conjunto de regras para buscar e manipular informações em um texto. Elas são usadas em uma variedade de linguagens de programação e aplicativos, incluindo editores de texto, ferramentas de busca e planilhas. Com expressões regulares, você pode buscar por padrões específicos em um texto, como um endereço de e-mail ou um número de telefone, e manipular ou substituir esses padrões de acordo com suas necessidades.

## Exemplo:

Por exemplo, vamos supor que você esteja fazendo uma aplicação que precisa de uma tela de login. Neste caso é comumente utilizado um número de telefone como meio de identificação da pessoa e como dito anteriormente, podemos representar um número de telefone usando expressões regulares. Podemos então, usar expressões regulares, por exemplo, para verificar se o conteúdo digitado pelo usuário corresponde a um padrão de texto que chamariamos de um número de telefone.

Eis um exemplo de programa que faz essa verificação, usando Python:

```python
import re

texto = "Meu número de telefone é (99) 99999-9999"

padrao = r"\(\d{2}\) \d{5}\-\d{4}"

resultado = re.search(padrao, texto)

if resultado:
    print(resultado.group(0))
```
Neste exemplo, usamos a expressão regular r"\(\d{2}\) \d{5}\-\d{4}" para buscar um número de telefone no formato (99) 99999-9999. A expressão regular corresponde a um parêntese aberto, seguido por dois dígitos, seguido por um parêntese fechado, seguido por um espaço, seguido por cinco dígitos, seguido por um traço e, finalmente, seguido por quatro dígitos.

## Sintaxe da Regex

Para descrever comportamentos especiais precisamos usar uma lista de caracteres especiais, eis aqui a lista 
de alguns desses caracteres e suas propriedades, adicionado de alguns exemplos.


* \ é utilizado como um caractere de escape.
* ^ pode ter duas funções, ou é uma âncora para o começo da frase, ou é um símbolo de negação.
    * Exemplo: "^a" procura por qualquer palavara que começa com a  "a"
    * Examplo: "[^0-9]" procura por qualquer caractere que não seja digito.
* $ é um caractere âncora para o fim da frase.
    * Exemplo: "b$" procura por frases com um "b" no final.
    * Exemplo: "^$" procura por frases vazias.
* { } define um quantificador de intervalo.
    * Exemplo: "a{2,3}" procura por frases que sejam "aa" ou "aaa".
* $\[ ] Define uma classe de caracteres, esperando uma ocorrência de um dessas.
    * Dentro do [ ] , podemos usar o sinal "-" para denotar um intervalo de caracteres
    * Exemplo: [a-z] caracteres de “a” até “z” em caixa baixa.
* Dentro do [ ], temos o ^ que nega o conjunto de caracteres.
    * Exemplo: "[^A-Z]"nega os caracteres do alfabeto em caixa alta.
* ( ) Agrupamento de caracteres (ou outros regexes).
* . Procura por qualquer caractere, exceto o símbolo de nova linha
    * Exemplo: ".a" procura por qualquer caractere seguido de um "a".
* \* procura por 0 ou mais expressões
* \+ (ou ∪) Procura por 1 ou mais expressões
* ? Procura por 0 ou 1 uma expressão
* | Separa possíveis expressões
    * Exemplo: "(a|b|c)a" procura por "aa", "ba" ou "ca".
* \d: essa expressão regular corresponde a qualquer dígito em um texto.
* \w: essa expressão regular corresponde a qualquer caractere alfanumérico em um texto.

## Compiladores

No contexto de compiladores, expressões regulares são importantes porque são usadas para definir as regras gramaticais da linguagem que está sendo compilada. De certa forma, podemos dizer que as linguagens de programção são convenções em como escrever um texto que possa ser traduzido que código que a máquina possa executar. Este texto possui padrões e por isso, as expressões regulares são usadas para reconhecer padrões nesse código fonte que correspondem a diferentes elementos da linguagem, como identificadores, números, operadores e símbolos de pontuação.

Por exemplo, considere a seguinte expressão regular:
``` 
[a-zA-Z][a-zA-Z0-9]*
```

Essa expressão regular corresponde a um identificador na maioria das linguagens de programação. Ela define que um identificador começa com uma letra maiúscula ou minúscula, seguida por zero ou mais letras maiúsculas, minúsculas ou dígitos.

Ao usar essa expressão regular em um compilador, o compilador pode reconhecer identificadores válidos na linguagem que está sendo compilada e gerar um erro de compilação se um identificador inválido for encontrado. Isso ajuda a garantir que o código fonte seja compilado corretamente e ajuda os programadores a escrever código mais consistente e legível.

## Conclusão
Expressões regulares são uma ferramenta poderosa para buscar e manipular informações em um texto. Elas podem ser usadas em uma variedade de linguagens de programação e aplicativos e são escritas usando caracteres especiais que representam padrões de texto. Espero que esta aula tenha sido útil para você entender melhor o que são expressões regulares e como usá-las para buscar padrões específicos em um texto.

## Links úteis

- [Expressões regulares em Javascript, definição, usos, e exemplos](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Regular_Expressions)
- [Expressões regulares em 100 segundos](https://www.youtube.com/watch?v=sXQxhojSdZM)
- [Ferramenta para testar e experimentar com regex](https://regexr.com/)
- [Papel cola para Regex](https://fireship.io/lessons/regex-cheat-sheet-js/)
