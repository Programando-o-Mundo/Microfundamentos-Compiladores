# Analisador Sintático - a segunda fase da Vanguarda

## O que você vai aprender...

- O que é um Analisador Sintático
- Como funciona o Analisador Sintático
- Qual é a importância do Analisador Sintático

## Requisitos

- Gramática
- Expressões regulares
- Analisador Léxico

## Definição e Exemplo

Um parser, também chamado de Analisador Sintático, é um programa que recebe uma entrada na forma de uma sequência de tokens (Geralmente essa sequência vem do Analisador Léxico) e verifica se estes estão de acordo com a sintaxe de uma determinada linguagem de programação. Se a entrada for válida de acordo com a sintaxe, o analisador normalmente construirá uma representação da entrada na forma de uma árvore de sintaxe abstrata (AST) ou alguma outra representação estruturada. Se a entrada não for válida, o analisador normalmente relatará um erro.

Existem muitos tipos diferentes de analisadores, mas a maioria deles segue um processo geral semelhante. Aqui está uma visão geral de alto nível de como um analisador pode funcionar:

  **1**-O analisador lê os tokens de entrada um por um, sendo esses tokens vindo do Analisador Léxico.
  
  **2**-Ele usa um conjunto de regras (essas regras sendo derivadas da gramática) para determinar que tipo de estrutura a entrada deve ter. A gramática especifica as combinações válidas de tokens que são permitidas na linguagem.
  
  **3**-À medida que o analisador lê a entrada, ele acompanha sua posição atual na entrada e o estado atual da análise (Obs.: aqui irá depender bastante sobre o tipo de implementação como ele irá acompanhar o estado atual da análise, isto é, se a implementação for de forma recursiva ou iterativa). Ele usa essas informações para decidir o que fazer a seguir.
  
  **4**-Se o token de entrada atual for válido de acordo com a gramática, o analisador normalmente consumirá o token e passará para o próximo. Ele também pode atualizar seu estado atual para refletir o fato de ter visto o token.
  
  **5**-Se o token de entrada atual não for válido, o analisador normalmente relatará um erro e interromperá a análise.

## Como funciona na prática

Agora, vamos colocar aqui de como um Parser funciona na prática. Suponhamos que temos a seguinte linha de código em uma linguagem de programação que parece com a linguagem C:

```c
x = 2 + 3 * y
```
A primeira etapa da análise sintática é a análise léxica, na qual o código fonte é dividido em tokens. No exemplo acima, os tokens seriam x, =, 2, +, 3, * e y. Em seguida, o Parser verifica a estrutura sintática desses tokens de acordo com as regras da gramática.

Para analisar a atribuição de valor a um identificador, a gramática da nossa linguagem pode ter uma regra como esta:

```
ATRIBUICAO → identificador '=' expressao
```

Essa regra indica que uma atribuição é composta por um indentificador, seguido do operador de atribuição (=), e uma expressão. Para analisar a linha de código x = 2 + 3 * y, o Parser começa verificando se o primeiro token é um identificador. Neste caso, é x, que é um identificador válido de acordo com as regras da gramática.

Em seguida, o Parser verifica se o segundo token é o operador de atribuição (=). Se sim, o Parser continua analisando a expressão após o operador de atribuição. A expressão é analisada de acordo com as regras da gramática da linguagem. Suponha que a nossa gramática define a seguinte regra para expressões aritméticas:

``` 
EXPRESSAO → termo (op_arit termo)*
```
Essa regra indica que uma expressão é composta por um termo, seguido de zero ou mais pares de um operador aritmético (op_arit) e outro termo. Cada termo pode ser um número, um identificador ou uma expressão entre parênteses.

No nosso exemplo, a expressão após o operador de atribuição é 2 + 3 * y. O Parser começa analisando o primeiro termo, que é o número 2. Em seguida, ele verifica se o próximo token é um operador aritmético (+). Se sim, o Parser analisa o próximo termo, que é a expressão 3 * y.

O Parser verifica que o primeiro termo dessa expressão é o número 3, seguido do operador aritmético (*) e da identificador y. Como a variável y é um identificador válido de acordo com as regras da gramática, o Parser conclui que a expressão 3 * y é válida.

O Parser retorna para a expressão original e verifica se ainda existem mais pares de operadores aritméticos e termos. Nesse caso, não existem mais, então a análise sintática da linha de código x = 2 + 3 * y é concluída com sucesso.

## Conclusão

Analisadores Sintáticos são um componente crítico de compiladores e interpretadores, pois são responsáveis por garantir que o programa de entrada esteja sintaticamente correto e possa ser processado corretamente pelo restante do compilador ou interpretador. Existem muitos algoritmos e técnicas que podem ser usados para implementar um analisador sintático, incluindo analisadores descendentes (como analisadores descendentes recursivos) e analisadores ascendentes (como analisadores LL e analisadores LR).

# Línks úteis

- [Compiladores para Humanos - Análise Sintática](https://johnidm.gitbooks.io/compiladores-para-humanos/content/part1/syntax-analysis.html)
- [Introdução a Análise Sintática](https://youtu.be/SegY2UEPCV4)
- [Algoritmo de Análise Sintática descendente recursivo](https://youtu.be/P2IhETKYM7U)
- [Aula 04 - Análise Sintática - Judson Santiago](https://youtu.be/FE5QwYEADak)
