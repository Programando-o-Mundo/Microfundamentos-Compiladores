# Analisador Semântico - a terceira fase da Vanguarda

# Gustavo Lopes Rodrigues

## O que você vai aprender...

- O que é o Analisador Semântico
- Como funciona a Analise Semântica
- Qual a importância da Análise Semântica

## Definição e exemplo

A análise semântica é um estágio de compilação no qual um compilador verifica o significado do programa que está sendo compilado e garante que ele esteja semanticamente correto. Isso inclui verificar itens como erros de tipo, variáveis não declaradas e outros problemas que podem afetar o significado do programa.

Durante a análise semântica, o compilador normalmente constrói uma tabela de símbolos, que é uma estrutura de dados que armazena informações sobre as variáveis, funções e outras entidades nomeadas usadas no programa. A tabela de símbolos permite que o compilador controle os nomes e tipos dessas entidades e garanta que sejam usados corretamente.

Por exemplo, considere o seguinte código na linguagem C:

```c
int main() {
  int x = y + z;
  return 0;
}
``` 


Durante a análise semântica, o compilador verificaria se as variáveis y e z foram declaradas e se possuem os tipos corretos. Se alguma dessas variáveis não tiver sido declarada, ou se tiverem o tipo errado, o compilador reportará um erro.

A análise semântica é normalmente realizada após a análise léxica e análise, e é uma etapa importante para garantir que o programa que está sendo compilado esteja bem formado e possa ser executado corretamente.
