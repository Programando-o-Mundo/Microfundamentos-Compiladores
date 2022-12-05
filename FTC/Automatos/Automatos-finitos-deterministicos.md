# Autômatos Finitos Determinísticos

# Gustavo Lopes Rodrigues

## Você vai aprender

* O que é um Autômato Finito Determinístico (AFD)
* Quais são os elementos que compõem um AFD
* Para o que utilizamos uma AFD

## Pré-requisitos

* Noções básicas

## Definição

Autômatos Finitos Determinísticos são, assim como o nome sugere,  máquinas com um número finito de estados, que aceitam ou rejeitam cadeia de símbolos (ou caractéres). Tipicamente, representamos AFDs utilizando um diagrama de transição de estados, como o exemplo abaixo feito no programa JFlap

AFDs são compostos por cinco (5) elementos importantes:

## Estados

Primeiramente temos o estado, que descreve a condição que uma cadeia está em determinado ponto do AFD. Temos dois
tipos de estados nos AFDs que são especiais:

### Estado inicial

É o ponto de partida para um AFD, é desse ponto que a nossa cadeia irá partir e então ser
passada para outros estados

### Estados Finais (ou Estados de Aceitação)

São pontos de paradas para os AFDs, se uma cadeia X que entrar em uma máquina, terminar sua leitura
em um Estado Final, quer dizer que tal cadeia foi aceita, caso contrário a mesma foi rejeitada

## Função de transição

Basicamente são funções que descrevem o requisito para uma cadeia transitar de um estado para outro.

Um exemplo prático seria o seguinte, vamos supor que queremos criar um AFD que leia a palavra "int", então teriamos
uma máquina parecida com isto:

Logo entrariamos na máquina onde o primeiro estado é o estado inicial, e teriamos o próximo estado "i", mas para passarmos para o estado "i" precisamos de uma função de transição que irá "consumir" o próximo elemento da cadeia, e verificar se o mesmo é um "i".

Uma observação importante: uma função de transição pode fazer transição em um próprio estado, fazendo disso um loop em um estado.

## Alfabeto

No contexto das AFDs, o alfabeto constitui os símbolos que são aceitos pelo AFD, então no nosso exemplo
anterior do AFD que lê a palavra "int", o nosso alfabeto é composto dos caracteres que compõem a palavra
"int", ou seja:

Alfabeto = {'i','n','t'}

## links úteis

[Veja outra aula sobre AFDs](https://edisciplinas.usp.br/pluginfile.php/5586355/mod_resource/content/1/ACH2043-Aula02-Cap1.1-AutomatosFinitosDetermin%C3%ADsticos.pdf)