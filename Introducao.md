# Introdução a Compiladores

# Gustavo Lopes Rodrigues

## O que você vai aprender

- O que é um Compilador.
- Qual é a diferença entre Compiladores e Interpretadores.
- Quais são as fases de um Compilador.

## Pré-requisitos

- Noções básicas de Fundamentos Teóricos da Computação.

## Definição

Até então na programação o que temos feito é sermos usuários de Linguagens de Programação como C, C++, Java, Python e entre outros. Agora
neste microfundamento, iremos aprender como fazer a nossa própria Linguagem a partir de um software chamado de Compilador.

Um Compilador é um programa que converte um programa escrito em uma linguagem fonte (como C++), em um terceiro programa escrito em linguagem alvo (Assembly ou L.M.)  L.M. = Linguagem de Máquina.

```mermaid
flowchart LR
    id1[\Programa Fonte/]
    id2(Compilador)
    id3[\Programa Alvo/]
    id4>Mensagem de Erro]

    subgraph Compilação
    id1 --> id2
    id2 --> id3
    end
    id2 --> id4
```

Vamos ver de perto um exemplo disso, aqui embaixo você irá encontrar um código talvez bem familiar.

```c
#include<stdio.h>

int main() {
  printf("Hello world!\n");
  return 0;
}
```

O que temos nesse exemplo é um código na linguagem C, que no nosso caso é a chamada **Linguagem Fonte** e o seu arquivo é o nosso **Programa Fonte**. Para a máquina essa sopa de letrinhas não possui nenhum significado, e podemos verificar isso, rodando o comando **file** do Linux neste arquivo, e verificando que o mesmo é apenas um arquivo de texto.

``` 
$ file main.c
main.c: C source, ASCII text
``` 

Para que este arquivo de texto tenha um significado para o computador, iremos chamar um compilador, neste caso como estamos lidando com a linguagem C
usarei o conhecido GCC (Gnu C Compiler).

```
$ gcc main.c
```

Ao invocarmos esse comando, estamos pedindo para o compilador compilar o nosso arquivo ```main.c``` e o tempo necessário para 
compilar o nosso arquivo, nós chamamos de **Tempo de compilação**. O resultado da execução desse comando irá gerar um arquivo 
chamada ```a.out```, que é o nosso **Programa Alvo**. Como estou em uma máquina Linux, o resultado do GCC será um programa escrito em Assembly x86_64(Essa seria a nossa **Linguagem Fonte**), específico para a arquitetura e o Sistema Operacional do meu computador.

Obs.: Podemos novamente confirmar o tipo de arquivo gerado pelo compilador, se rodarmos o comando **file**, desta vez no arquivo ```a.out```. O resultado desse comando nos informa que o nosso ```a.out``` é nada mais do que um Executable and Linkable File (ELF) de 64 bits, um padrão de arquivos executáveis no Linux.

``` 
$ file a.out
a.out: ELF 64-bit LSB pie executable, x86-64...
``` 

Agora vamos então rodar esse nosso programa compilado.

```
$ ./a.out
Hello World!
``` 


Obs.: Se eu mandar esse mesmo ```a.out``` para outra máquina Linux, o meu programa irá rodar, mas se eu mandar para outro Sistema Operacional
(como o Windows) ou para um computador com outra arquitetura (Como ARM ou Risc-V), esse código não irá rodar.

Aqui, quando executamos esse comando estamos rodando o nosso programa, o intervalo em que um programa permanece em execução
é chamado de **Tempo de execução**.

## Interpretador

Muitos de vocês já devem ter utilizado linguagens com Python, Java, Javascript e entre outras. Essas linguagens possuem um programa chamado de Interpretador.

Diferente do compilador que tem como objetivo gerar um arquivo escrito na Linguagem Alvo, o Interpretador é um programa que lê um arquivo (código fonte) e interpreta tal arquivo e converte em código executável linha por linha.

Nós não iremos entrar em grande detalhe sobre o funcionamento desses programas, pois não é o foco da disciplina, a coisa mais importante que você precisa entender aqui, é diferente do compilador, o Interpretador não irá gerar um arquivo com a Linguagem Alvo, pois o código será executado na medida que for analisado. Além disso, o tempo de compilação e execução são diferentes, aqui o tempo de compilação e execução são os mesmos.

## Fases do Compilador

```mermaid
flowchart TD
    B(Analisador \n Léxico)
    A{Programa \n Fonte} 
    C(Analisador \nSintâtico)
    D(Analisador \nSemântico)
    E(Gerador de Código \n Intermediário)
    F(Otimizador de \nCódigo)
    G(Gerador de Código)
    H{Programa \n Alvo}

    Tab[(Gerenciador da \n Tabela de Símbolos)]

    Inicio((Ponto Inicial))

    subgraph FrontEnd [" Front End (Vanguarda) "]
    direction LR
    B --> C
    C --> D
    end 

    subgraph MiddleEnd [" Middle End"]
    direction LR
    E --> F
    end

    subgraph BackEnd [" Back End (Retaguarda) "]
    direction LR
    G 
    end 

    Err[(Gerenciador de \n Erros)]

    subgraph Tabela [" "]
        Tab
    end 

    subgraph Gerenciadores [" "]
        Tabela
        Erros 
    end 

    subgraph Compilador [" Compilador "]
        direction LR
        Inicio --> FrontEnd
        FrontEnd --> MiddleEnd
        MiddleEnd --> BackEnd
        Gerenciadores <--> FrontEnd
        Gerenciadores <--> MiddleEnd
        Gerenciadores <--> BackEnd
    end 

    subgraph core [" "]
        A --> Compilador
        Compilador --> H
    end 

    subgraph Erros [" "]
        Err 
    end 

    

    style B fill:#43f,stroke:#333,stroke-width:4px
    style C fill:#43f,stroke:#333,stroke-width:4px
    style D fill:#43f,stroke:#333,stroke-width:4px
    style E fill:#164f,stroke:#333,stroke-width:4px
    style F fill:#164f,stroke:#333,stroke-width:4px
    style G fill:#543,stroke:#333,stroke-width:4px
    style Err fill:#a33,stroke:#333,stroke-width:4px
    style Tab fill:#3489,stroke:#333,stroke-width:4px

```

Agora que temos uma noção geral do compilador, podemos agora falar sobre as fases do Compilador. O Compilador pode ser dividido em três seções, o Front-End (Vanguarda), o Middle-End e o Back-End (Retaguarda).

## Front-End

O Front-End possui três componentes, o Analisador Léxico, Analisador Sintático e o Analisador Semântico

### Analisador Léxico

O Analisador Léxico, também chamado de "A fase de Scanning" é a parte onde o Compilador irá fazer a tokenização do código fonte. A sequência  de  caracteres  do programa-fonte é lida da esquerda para a direita em busca de elementos da linguagem (tokens). Responsável em identificar lexemas no programa-fonte, verificando a correção “ortográfica” do código e os tokens correspondentes.

Exemplo de erro do Analisador Léxico seria esse código:

```c
#include<stdio.h>

int main() {
    int a = 10.0.0;
    printf("%d\n", a);
    return 0;
}
``` 

Não existe o lexema "10.0.0" na linguagem C.

#### Lexemas

Lexemas é a forma na qual um token é escrito no programa fonte. Quando o programa for analisado, os lexemas serão lidos e então convertidos para tokens que o programa fonte pode compreender.

Lexemas podem ser escritos ou de forma literal ou usando regex:

| tokens | lexemas |
---------|----------
id | (\c $\cup$ _)(\c $\cup$ \d  $\cup$ _)*
int | "int"
float | "float"
\+ | \+
inc | ++ 

Obs.: id = identificador

Outras observações importantes:

* Espaço em branco não é token e sim um delimitador léxico
* Quebra-de-linha em algumas linguagens é um Token, em outras linguagens não
* Comentário não é token, nem a mensagem, nem os seus delimitadores
* Diretivas (#define) (#include) são comandos para o compilador ( não tokens )


### Analisador Sintático

Também chamado de Análise Hierárquica, essa fase é responsável em agrupar os tokens em estruturas hierárquicas seguindo as regras de produção da gramática. Responsável por agrupar os itens léxicos (tokens) em estruturas hierárquicas. Cada token identificado pelo Analisador Léxico é armazenado na tabela de símbolos e sua posição verificada através da gramática.

Exemplo de erro do Analisador Léxico seria esse código

```c
#include<stdio.h>

int main() {
    int b = 5;
    int a = 3;
    int c = + a b;
    printf("O resultado de a + b é %d", c);
    return 0;
}
``` 
De acordo com a gramática, o + deveria vir entre os identificadores **a** e **b**, porém isso não acontece, gerando um erro.

### Analisador Semântico

Nesta fase, os componentes do programa são checados para se garantir sentido às estruturas. Responsável por verificar a coerência das estruturas, quanto ao seu contexto, tipos de operandos e operadores, declaração de variáveis e constantes, entre outros.

Exemplo de erro do Analisador Semântico seria:

```c
#include<stdio.h>

int main() {
    int a = 10.7;
    printf("%d\n", a);
    return 0;
}
``` 

Neste caso, temos uma incompatibilidade de tipos, pois o identificador é do tipo "int" mas o valor atribuído é um "float".

## Middle-end

### Geração de Código Intermediário

Responsável por representar as estruturas  sintáticas  encontradas  na  forma  de  um  programa  para uma  máquina  abstrata.  Esta  representação  intermediária facilita a conversão do programa fonte para o programa alvo. 

```mermaid
classDiagram
class LinguagemCLike
LinguagemCLike : int a = 5
LinguagemCLike : int b = 3
LinguagemCLike : int c = 7
LinguagemCLike : int d = a + b * c

direction LR
LinguagemCLike --> CodigoIntermediario

class CodigoIntermediario 
CodigoIntermediario 
CodigoIntermediario  : a = 5
CodigoIntermediario  : b = 3
CodigoIntermediario  : c = 7
CodigoIntermediario  : t1 = b * c
CodigoIntermediario  : t2 = t1 + a
CodigoIntermediario  : d = t2

```

Obs.: t1 e t2 são variáveis temporárias

### Otimização de Código

Permite melhorar a representação intermediária, com o objetivo de produzir um código final mais eficiente. 

```mermaid
classDiagram

class CodigoIntermediario 
CodigoIntermediario  : b = 3
CodigoIntermediario  : c = 7
CodigoIntermediario  : t1 = b * c
CodigoIntermediario  : d1 = t1
CodigoIntermediario  : t1 = d1 
CodigoIntermediario  : t2 = t1+3
CodigoIntermediario  : d = t2

direction LR
CodigoIntermediario --> OtimizacaoPeephole

class OtimizacaoPeephole
OtimizacaoPeephole  : b = 3
OtimizacaoPeephole  : c = 7
OtimizacaoPeephole  : t1 = b * c
OtimizacaoPeephole  : t2 = t1+3
OtimizacaoPeephole  : d = t2
```

## Back-end

### Gerador de Código

Realiza a conversão do código intermediário para o código alvo. 

# "Primos" do Compilador

Além do Compilador, seria interessante você entender mais dois programas que são fundamentais na geração do código.

## Montador

O primeiro deles é o montador, alguns compiladores possuem um montador embutido, mas a sua função é traduzir o código gerador pelo Compilador (Assembly) e transformar em uma representação intermediária chamada de código objeto. Este código de montagem é uma versão mnemônica do código de máquina, onde é utilizado nomes em lugar de código de máquina. Para transformar esse código, em um programa que a máquina possa ler, iremos usar o segundo programa, o Linkeditor

## Linkeditor 

O Linkeditor, Ligador ou Editor de Ligações tem como objetivo permite criar um único módulo de carga, a partir de vários arquivos de código objeto. Isso acontece pois vamos supor que estamos trabalho em um projeto com vários arquivos diferentes, cada um deles vai gerar o seu próprio arquivo de código objeto. No final da compilação, cabe ao Linkeditor pegar todos esses arquivos e juntá-los em um executável apenas.
