# Introdução a Compiladores

# Gustavo Lopes Rodrigues

## O que você vai aprender

- O que é um Compilador
- Qual é a diferença entre Compiladores e Interpretadores
- Quais são as fases de um Compilador

## Pré-requisitos

- Noções básicas de FTC

## Definição

Até então na programação o que temos feito é ser usuários de Linguagens de Programação, como C, C++, Java, Python e entre outros. Agora
nessa disciplina, iremos aprender como fazer a nossa própria Linguagem, a partir de um software chamado de Compilador.

Um Compilador é um programa que converte um programa escrito em uma linguagem fonte, em um terceiro programa escrito em linguagem 
alvo (Assembly ou L.M)  L.M = Linguagem de Máquina

Vamos ver de perto um exemplo disto, aqui embaixo você irá encontrar um código talvez bem familiar.

```c
#include<stdio.h>

int main() {
  printf("Hello world!\n");
  return 0;
}
``` 
O que temos neste exemplo é um código na linguagem C, que para o nosso caso é a tão chamada **Linguagem Fonte**. Para a máquina essa
sopa de letrinhas não possui nenhum significado. Podemos verificar isso, rodando o comando **file** do Linux neste arquivo, e verificando
que o mesmo é apenas um arquivo de texto.

``` 
$ file hello.c
hello.c: C source, ASCII text
``` 

Para dar significado a esse arquivo de texto para o computador, iremos chamar um compilador, neste caso como estamos lidando com a linguagem C
usarei o conhecido GCC (Gnu C Compiler).

```
$ gcc main.c
```

Ao invocarmos esse comando, estamos pedindo para o compilador compilar o nosso arquivo ```main.c``` e o tempo necessário para 
compilar o nosso arquivo, nós chamamos de **Tempo de compilação**. O resultado final da compilação nesse caso, irá gerar um arquivo 
chamada a.out, que é a nossa linguagem alvo. Como estou em uma máquina Linux, o resultado do GCC será um programa escrito em Assembly x86_64, 
específico para a arquitetura e o Sistema Operacional do meu computador.

Obs.: Se eu mandar esse mesmo a.out para outra máquina Linux, o meu programa irá rodar, mas se eu mandar para outro Sistema Operacional
(como o Windows) ou para um computador com outra arquitetura (Como ARM ou Risc-V), esse código não irá rodar.

Obs2.: Podemos novamente confirmar o tipo de arquivo gerado pelo compilador, se rodarmos o comando **file** no arquivo a.out

``` 
$ file a.out
hello: hello: ELF 64-bit LSB pie executable, x86-64...
``` 

Agora vamos então rodar esse nosso programa compilado.

```
$ ./a.out
Hello World!
``` 

Aqui, quando executamos esse comando estamos rodando o nosso programa, e o intervalo em que um programa permanece em execução
chamamos de **Tempo de execução**.

## Interpretador

Programas que leem um código fonte e interpreta tal e converte em código executável
o código.

Aqui, diferente do compilador onde o tempo de compilação e execução são diferentes, aqui o 
tempo de compilação e execução são os mesmos.
