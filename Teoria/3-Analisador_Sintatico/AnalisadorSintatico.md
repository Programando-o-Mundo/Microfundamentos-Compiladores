# Analisador Sintático - a segunda fase da Vanguarda

# Gustavo Lopes Rodrigues

## O que você vai aprender...

- O que é um Analisador Sintático
- Como funciona o Analisador Sintático
- Qual é a importância do Analisador Sintático

## Definição e Exemplo

Um parser, também chamado de Analisador Sintático, é um programa que recebe uma entrada na forma de uma sequência de tokens (Geralmente essa sequência vem do Analisador Léxico) e verifica se estes estão de acordo com a sintaxe de uma determinada linguagem de programação. Se a entrada for válida de acordo com a sintaxe, o analisador normalmente construirá uma representação da entrada na forma de uma árvore de sintaxe abstrata (AST) ou alguma outra representação estruturada. Se a entrada não for válida, o analisador normalmente relatará um erro.

Existem muitos tipos diferentes de analisadores, mas a maioria deles segue um processo geral semelhante. Aqui está uma visão geral de alto nível de como um analisador pode funcionar:

  **1**-O analisador lê os tokens de entrada um por um.
  
  **2**-Ele usa um conjunto de regras (essas regras sendo derivadas da gramática) para determinar que tipo de estrutura a entrada deve ter. A gramática especifica as combinações válidas de tokens que são permitidas na linguagem.
  
  **3**-À medida que o analisador lê a entrada, ele acompanha sua posição atual na entrada e o estado atual da análise (Obs.: aqui irá depender bastante sobre o tipo de implementação como ele irá acompanhar o estado atual da análise, isto é, se a implementação for de forma recursiva ou iterativa). Ele usa essas informações para decidir o que fazer a seguir.
  
  **4**-Se o token de entrada atual for válido de acordo com a gramática, o analisador normalmente consumirá o token e passará para o próximo. Ele também pode atualizar seu estado atual para refletir o fato de ter visto o token.
  
  **5**-Se o token de entrada atual não for válido, o analisador normalmente relatará um erro e interromperá a análise.

Analisadores Sintáticos são um componente crítico de compiladores e interpretadores, pois são responsáveis por garantir que o programa de entrada esteja sintaticamente correto e possa ser processado corretamente pelo restante do compilador ou interpretador. Existem muitos algoritmos e técnicas que podem ser usados para implementar um analisador sintático, incluindo analisadores descendentes (como analisadores descendentes recursivos) e analisadores ascendentes (como analisadores LL e analisadores LR).

# Línks úteis

- [Compiladores para Humanos - Análise Sintática](https://johnidm.gitbooks.io/compiladores-para-humanos/content/part1/syntax-analysis.html)
- [Introdução a Análise Sintática](https://youtu.be/SegY2UEPCV4)
- [Algoritmo de Análise Sintática descendente recursivo](https://youtu.be/P2IhETKYM7U)
- [Aula 04 - Análise Sintática - Judson Santiago](https://youtu.be/FE5QwYEADak)
