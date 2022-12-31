# Analisador Semântico - a terceira fase da Vanguarda

# Gustavo Lopes Rodrigues

## O que você vai aprender...

- O que é o Analisador Semântico
- Como funciona a Analise Semântica
- Qual a importância da Análise Semântica

## Definição e exemplo

A análise semântica é a terceira fase da compilação, no qual um compilador verifica o significado das declarações e frases que estão sendo compiladas e garante que estas estejam semanticamente corretas. Isso inclui verificar itens como erros de tipo, variáveis não declaradas e outros problemas que podem afetar o significado do programa.

Durante a análise semântica, a tabela de símbolos será frequentemente utilizada pois é esta que irá permitir que o compilador controle os nomes e tipos dos tokens e garanta que sejam usados corretamente.

Por exemplo, considere o seguinte código na linguagem C:

```c
int main() {
  int x = y + z;
  return 0;
}
``` 


Durante a análise semântica, o compilador verificaria se as variáveis y e z foram declaradas e se possuem os tipos corretos. Se alguma dessas variáveis não tiver sido declarada, ou se tiverem o tipo errado, o compilador reportará um erro.

A análise semântica é normalmente realizada após a análise léxica e análise, pois é uma análise feita em cima da árvore sintâtica, e é uma etapa importante para garantir que o programa que está sendo compilado esteja bem formado e possa ser executado corretamente.

# Links úteis

- [Compiladores para humanos - Análise Semântica](https://johnidm.gitbooks.io/compiladores-para-humanos/content/part1/semantic-analysis.html)
- [Análise Semântica - Vídeo do "Aulas de Computação"](https://youtu.be/UU6XC17kEDs)
- [Aula 10 - Análise Semântica - Judson Santiago](https://www.youtube.com/watch?v=msv_0QqXz7s&list=PLX6Nyaq0ebfhI396WlWN6WlBm-tp7vDtV&index=12)

