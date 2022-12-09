# Gramáticas

# Gustavo Lopes Rodrigues

## Você vai aprender

* O que são gramáticas

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

As produções são os itens produzidos pelas variáveis, por exemplo, neste caso, quando dizemos que S produz “aSb” dizemos que isto é a produçãode S.

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

## Gramáticas regulares (tipo 3)

Uma gramática é dita regular, quando a mesma possui apenas derivação ou para a esquerda ou para a direita, ela não pode misturar derivações.

## Converter Autômato para uma gramática ou vice versa

S → aA
A → aA | bA | λ

## Gramáticas Livres de Contexto (tipo 2)

São gramáticas caracterizadas pela V → α onde α pertence a expressão (V U T*).

Em outras palavras, quando uma gramática é livre de contexto, suas variáveis no lado esquerdo da produção só possuem a variável em si, e nada mais, elas são independentes, por isso que dizemos que ela é livre ou independente de contexto.

Um exemplo disso seria a seguinte gramática:

S → aAb | ab

A → aA | λ

Uma maneira simples de entender isso, seria com uma gramática sensível ao contexto:

aA → aa

A gramática acima ela não é livre de contexto, pois sua variável a esquerda (A) é acompanhada de um terminal (a), logo a mesma é dependente do contexto na qual ela é inserida.

Outra coisa importante a notar, é que toda gramática que é do tipo 3 (regular) é livre de contexto, porém, nem toda gramática livre de contexto é regular.
