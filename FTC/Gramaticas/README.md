# Gramáticas

## Você vai aprender

* O que são gramáticas
* Quais são os componentes de uma gramática
* Quais são os tipos de gramática

## Pré-requisitos

* Noções básicas

## Definição

Pode se definir como uma quádrupla com quatro itens:

* V → Variáveis (geralmente denotadas com letras maiúsculas: [A-Z])
* T → Terminais (geralmente denotadas com letras minúsculas: [a-z] ou algumas letras gregas)
* P → Produções
* S → Variável de partida

Um exemplo de gramática seria:

S → aSb

S → aB

B → b

## Variáveis

Variáveis geralmente são sempre representadas por caracteres em maiúsculo, então { S, B } neste caso são as nossas variáveis.

**S** → a**S**b

**S** → a**B**

**B** → b

## Terminais

Já as terminais são nada mais que os símbolos do nosso alfabeto, neste caso, o nosso alfabeto pode ser definido como { a, b } , já que são os únicos terminais presentes na gramática.

S → **a**S**b**

S → **a**B

B → **b**

## Produções

As produções são os itens produzidos pelas variáveis, por exemplo, neste caso, quando dizemos que S produz “aSb” dizemos que isto é a produção de S.

**S → aSb**

**S → aB**

**B → b**

## Variável de partida

Por fim, toda gramática precisa de uma Variável de partida que é onde toda gramática será inicializada, ou seja, toda gramática precisa de um ponto de partida.

**S** → a**S**b

**S** → aB

B → b

## Qual é o objetivo das gramáticas?

Dado uma linguagem qualquer, teremos dois elementos importantes, primeiro teremos os mecanismos aceitadores que seriam os nossos autômatos finitos, e os mecanismos geradores, que seriam as gramáticas. As gramáticas no final das contas, tem como objetivo a geração de palavras válidas para a minha linguagem.Tipos de gramáticas

## Gramática Linear

Uma gramática é dita linear quando possuem no máximo um símbolo não terminal (ou seja, uma variável) no lado direito de suas produções.

Por exemplo:

S → aB

S → Ab

S → b

observe que no lado direito da produção (depois da →) possuímos apenas uma variável, não importa qual variável seja essa, o importante é a quantidade.

Dentro das gramáticas lineares, temos dois tipos mais conhecidos de gramáticas. 

## Gramática Linear à esquerda

Quando uma gramática é linear para a esquerda, suas produções possuem as variáveis terminais a esquerda das variáveis,ou seja:

A → Ba | b | b

A → Ab | Bb | a

Perceba que as terminais {a,b} estão sempre do lado esquerdo das variáveis.

## Gramática Linear à direita

Seguindo a mesma lógica anterior, gramáticas que são lineares a direita, possuem seus terminais a direita das variáveis, ou seja:

A → aA | aB | a

B → bB | aB | b

## Hierarquia de Chomsky

A hierarquia de gramáticas de acordo com Chomsky é uma classificação das gramáticas formais em quatro níveis hierárquicos, que são nomeados em homenagem ao linguista Noam Chomsky. Essa hierarquia é útil para entender as propriedades das linguagens que podem ser geradas por cada tipo de gramática.

Os quatro níveis da hierarquia de gramáticas de Chomsky são:

### Gramáticas tipo 0 (ou gramáticas irrestritas): 

São as gramáticas mais poderosas e permitem gerar qualquer linguagem formal. Essas gramáticas são definidas por um conjunto de regras de produção que não impõem restrições sobre a forma das regras ou a ordem em que elas podem ser aplicadas.

### Gramáticas tipo 1 (ou gramáticas sensíveis ao contexto): 

Essas gramáticas permitem gerar linguagens formais que são sensíveis ao contexto. Isso significa que a estrutura sintática das sentenças geradas por essas gramáticas depende do contexto em que as regras de produção são aplicadas. As regras de produção dessas gramáticas são restritas de tal forma que o lado esquerdo de cada regra deve ter pelo menos um símbolo a mais do que o lado direito.

Observe o exemplo abaixo:

aA → aa

A gramática acima ela não é livre de contexto, pois sua variável a esquerda (A) é acompanhada de um terminal (a), logo a mesma é dependente do contexto na qual ela é inserida.

### Gramáticas tipo 2 (ou gramáticas livres de contexto): 

São gramáticas onde todas as regras de produção são da forma "não-terminal → cadeia de símbolos", onde um não-terminal pode ser substituído por qualquer cadeia de símbolos, independentemente do contexto. Essas gramáticas permitem gerar linguagens formais que podem ser descritas por uma árvore sintática, onde cada não-terminal representa uma subárvore.

São gramáticas caracterizadas pela V → α onde α pertence a expressão (V U T*).

Em outras palavras, quando uma gramática é livre de contexto, suas variáveis no lado esquerdo da produção só possuem a variável em si, e nada mais, elas são independentes, por isso que dizemos que ela é livre ou independente de contexto.

Obs.:  toda gramática que é do tipo 3 (regular) é livre de contexto, porém, nem toda gramática livre de contexto é regular.

Um exemplo disso seria a seguinte gramática:

S → aAb | ab

A → aA | λ

### Gramáticas tipo 3 (ou gramáticas regulares): 

Essas gramáticas são as mais restritas e geram apenas linguagens regulares. Essas gramáticas são definidas por um conjunto de regras de produção que permitem apenas uma substituição de um único símbolo não-terminal por uma cadeia de símbolos terminais ou um único símbolo terminal. As regras de produção dessas gramáticas são geralmente escritas na forma "não-terminal → terminal" ou "não-terminal → terminal não-terminal".

Ou seja, uma gramática é dita regular, quando a mesma possui apenas derivação ou para a esquerda ou para a direita, ela não pode misturar derivações.

## Converter Autômato para uma gramática ou vice versa

S → aA
A → aA | bA | λ

Essa hierarquia de gramáticas é importante porque cada tipo de gramática tem suas próprias propriedades e limitações, o que influencia a capacidade de um programa ou sistema de computação em reconhecer ou gerar uma linguagem formal específica. Por exemplo, as linguagens regulares podem ser facilmente reconhecidas e processadas por autômatos finitos, enquanto as linguagens sensíveis ao contexto podem ser reconhecidas por autômatos de pilha. Já as linguagens livres de contexto e irrestritas exigem algoritmos mais complexos e poderosos para o reconhecimento e processamento.

## Links úteis

- [Teoria da Computação 33 - Introdução as gramáticas formais e exercícios de geração de gramáticas](https://youtu.be/4BKgtnQt1pQ)
- [Teoria da computação 34 - Tipos de Gramáticas e conversão de Gramáticas para AF's e vice-versa.](https://youtu.be/Y9gYuyP3xkI)
