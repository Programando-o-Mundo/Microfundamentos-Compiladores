# Implementando a Tabela de Simbolos

## Você vai aprender...

- Como implementar a Tabela de Símbolos usando Hash

## Pré-requisitos

- [Introdução a Compiladores](../../Introducao.md)
- [Teoria-Tabela de Símbolos](Teoria.md)

## Implementando em código

Aqui nos iremos dar uma pequena olhada em como iremos implementar a Tabela de Símbolos para ser usada na nossa linguagem de programação "X". 
Para o nosso caso irei usar uma tabela hash. Já querendo deixar claro isto, mas esta não é a única maneira de implementar uma Tabela de Símbolos, mas esta é uma das mais comuns, devido ao fato que você pode usá-la para inserir, procurar e deletar itens de forma bem rápida e eficiente.

Como estaremos utilizando C++, iremos utilizar a classe [unordered_map](https://en.cppreference.com/w/cpp/container/unordered_map) da biblioteca padrão do C++. Essa classe é muito boa para o nosso caso de uso, já que as chaves não serão armazenadas de forma ordenada (pois não precisamos dos símbolos estarem ordenados) logo diminuindo a complexidade da estrutura, com um tempo de busca O(1).


# Links úteis

- [Slides de Compiladores da UFMG(pg 20-32)](https://homepages.dcc.ufmg.br/~bigonha/Cursos/comp-slides-p4.pdf)
- [Compiladores | Aula 08 - Tabela de Símbolos | Escopos | Blocos Aninhados | Implementação](https://youtu.be/k2jm1uplI5Y)
