# Tabela de Símbolos

# Gustavo Lopes Rodrigues 

## Você vai aprender...

- O que é a Tabela de Símbolos
- Qual é a importância da Tabela de Símbolos

## Pré-requisitos

- Ter visto a aula de Introdutória de Compiladores 

## Definição

A tabela de símbolos é uma Estrutura de Dados usada por linguagens de programação e Compiladores para armazenar informações sobre símbolos usados em um programa, estes símbolos podem ser variáveis, funções, constantes, palavras reservadas e entre outros. Esta estrutura permite que o compilador (ou interpretador) procure rapidamente a definição e as propriedades de um símbolo enquanto processa o programa.

Uma tabela de símbolos normalmente inclui as seguintes informações para cada símbolo:

- O nome do símbolo
- O tipo do símbolo (por exemplo, inteiro, string, etc.)
- O escopo do símbolo (ou seja, o escopo do programa onde o símbolo é visível)
- A localização do símbolo na memória (por exemplo, o endereço de uma variável na memória)

As tabelas de símbolos são usadas para várias finalidades em diferentes partes do compilador, como verificar a sintaxe e a semântica de um programa, gerar código de máquina e otimizar o desempenho do código. Eles são uma parte importante da infraestrutura do compilador ou do interpretador, pois permitem que o programa faça referência e manipule símbolos de maneira consistente e eficiente.

Tais símbolos armazenados na tabela são coletados pelas fases de análise do compilador (Analisador Léxico) e então as fases posteriores (Analise Sintática e Semântica) podem adicionar informações a essa entrada, como tipo do identificador, seu uso, sua posição de armazenamento, etc.

# Links úteis

- [Slides de Compiladores da UFMG(pg 20-32)](https://homepages.dcc.ufmg.br/~bigonha/Cursos/comp-slides-p4.pdf)
- [Compiladores | Aula 08 - Tabela de Símbolos | Escopos | Blocos Aninhados | Implementação](https://youtu.be/k2jm1uplI5Y)
