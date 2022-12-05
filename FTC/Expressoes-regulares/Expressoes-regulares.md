# Expressões regulares

# Gustavo Lopes Rodrigues

## Você vai aprender

* O que são Expressões regulares
* Alguns exemplos
* Como são utilizadas

## Pré-requisitos

* Noções básicas

## Definição

Você provavelmente já deve ter visto a placa de um carro, um endereço de email ou até mesmo
um número de telefone. Todas essas coisas por mais diferentes que sejam, todas elas tem uma coisa
em um comum, todas podem ser descritas utilizando expressões regulares.

Expressões regulares nada mais é que um sistema que provê uma forma concisa e flexível para identificar caracteres de interesse. Usamos bastante essa ferramenta como mecanimos de manipulação ou pesquisa de textos contidos em Strings.

Como citado anteriormente, um exemplo de expressão regular é nas placas de carros. Aqui no Brasil usamos três caractéres, seguidos de um traço(-) e depois por quatro números, por exemplo: GJD-3832. Outro exemplo seria o e-mail, onde temos um nome, seguido por um "@" depois temos o domínio.

Todas essas formas que falamos agora pouco descrevem uma expressão regular, mas agora, podemos descrever isso de outra forma? Claro que sim, e para isso temos o sistema de caractéres especiais:

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
* [ ] Define uma classe de caracteres, esperando uma ocorrência de um dessas.
    * Dentro do [ ] , temos o - denota um intervalo de caracteres
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
