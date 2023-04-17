
# Gramáticas LL(1) e recursão a esquerda

## Você vai aprender

- O que são gramáticas LL(1)
- Quais são suas caractéristicas
- Como converter gramáticas para LL(1)

## Requisitos

- Definição básica

## Definição

As gramáticas LL(1) são um tipo de gramática livre de contexto que possuem a propriedade de serem analisáveis sem necessitar de backtracking.
O primeiro "L" em LL(1) significa escanear a entrada da esquerda para a direita (Left-to-right), o segundo "L" significa produzir uma derivação mais à esquerda e o "1" 
significa usar um símbolo de lookahead em cada etapa para tomar decisões de parsing, ou seja precisa de apenas um símbolo de lookahead da entrada. Em outras
palavras, uma gramática LL(1) também é uma gramática "Left-to-right, Leftmost derivation, 1 lookahead".

## Restrições

Para que uma gramática seja LL(1), ela deve seguir algumas restrições:

- As produções não podem ter recursão à esquerda.
- Cada não-terminal deve ter um conjunto de produções que começam com um conjunto de terminais disjuntos (sem sobreposição).
- Para cada não-terminal, não pode haver duas produções cujos conjuntos de terminais iniciantes tenham interseção não-vazia.

Essas restrições garantem que o DPDA possa decidir qual produção aplicar apenas olhando o próximo símbolo da entrada. A 
gramática LL(1) é importante porque ela pode ser usada para construir analisadores sintáticos eficientes, como os analisadores 
sintáticos preditivos LL(1), que são fáceis de implementar e podem ser usados em muitas linguagens de programação.

Os analisadores sintáticos preditivos LL(1) são capazes de analisar a entrada sem fazer backtracking (volta atrás) e, portanto, 
são mais eficientes do que outros tipos de analisadores sintáticos. Eles são amplamente usados em ferramentas de desenvolvimento 
de linguagem, como compiladores, interpretadores, IDEs e outras ferramentas que dependem da análise sintática de uma linguagem formal.

## Recursão à esquerda

A recursão à esquerda em uma gramática é um problema que pode levar a ambiguidade ou dificuldades em reconhecer e gerar sentenças. 
Para remover a recursão à esquerda, pode-se utilizar o processo de fatoração à esquerda e substituição, que é um algoritmo que 
transforma uma gramática recursiva à esquerda em uma gramática equivalente que não é recursiva à esquerda.

O processo de fatoração à esquerda e substituição envolve os seguintes passos:

- Identificar as regras de produção que causam a recursão à esquerda.

- Fatorar as regras de produção que causam a recursão à esquerda, criando uma nova regra que não tenha recursão à esquerda.

- Substituir a regra original pela nova regra fatorada nas outras regras que a referenciam.

- Repetir os passos 2 e 3 até que não haja mais recursão à esquerda na gramática.

### Exemplo

Por exemplo, considere a seguinte gramática com recursão à esquerda:

S → S a | a

Para remover a recursão à esquerda, podemos fatorar a regra S → S a da seguinte forma:

S → a S'
S' → a S' | ε

A nova regra S' é adicionada para lidar com os casos em que a recursão à esquerda ocorria. A regra original S → S a foi substituída pela nova regra S → a S'.

A gramática resultante é equivalente à gramática original e não possui mais recursão à esquerda. Este processo pode ser aplicado em outras gramáticas com recursão à esquerda para torná-las mais adequadas para serem reconhecidas e processadas por sistemas de computação.
