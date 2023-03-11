# Uma Introdução para Assembly

## O que é a linguagem Assembly x86_64?

A linguagem Assembly é uma linguagem de baixo nível que permite escrever programas diretamente em linguagem de máquina. A linguagem Assembly x86_64 é uma versão da linguagem Assembly que é projetada para ser executada em processadores Intel ou AMD de 64 bits.

Ao contrário das linguagens de alto nível, como C, Python ou Java, a linguagem Assembly x86_64 é muito mais difícil de ser lida e escrita pelos humanos, pois é composta por uma sequência de instruções de baixo nível, como mov, add e jmp, que são executadas diretamente pelo processador.

Neste primeira aula, vamos criar o nosso primeiro "Hello World" porém em Assembly x86_64

## Hello World em Assembly!

Para criar um programa Hello World em Assembly x86_64 e compilar em uma máquina Linux, siga os seguintes passos:

Abra um editor de texto ou a sua IDE de escolha e crie um novo arquivo com extensão ".asm". Digite o seguinte código:

```asm
section .data
msg db 'Hello, world!',0

section .text
global _start

_start:
    ; write message to stdout
    mov eax, 4 ; system call for write
    mov ebx, 1 ; file descriptor for stdout
    mov ecx, msg ; message to write
    mov edx, 13 ; length of message
    syscall ; call kernel

    ; exit program
    mov eax, 1 ; system call for exit
    xor ebx, ebx ; exit with return code 0
    syscall ; call kernel
```

Em código assembly, como pode se perceber, é divido em duas seções principais: .data e .text, vamos dar uma olhada na função de cada uma:

## Seção data

A seção .data é usada para definir variáveis globais ou estáticas que serão usadas no programa. As variáveis podem ser inicializadas com valores ou não, e são armazenadas na seção de dados do programa. Por exemplo:

```asm
section .data
msg db 'Hello, world!',0
```

Isso define uma variável chamada "hello" que contém a string "Hello, world!" seguida de um byte nulo (0).

## Seção text

A seção .text é usada para definir o código do programa. Isso inclui todas as instruções e rotinas que são executadas pelo programa. Por exemplo:

```asm
section .text
global _start

_start:
    ; write message to stdout
    mov eax, 4 ; system call for write
    mov ebx, 1 ; file descriptor for stdout
    mov ecx, msg ; message to write
    mov edx, 13 ; length of message
    syscall ; call kernel
```

Nesse exemplo, a seção .text contém o código principal do programa, incluindo a definição do ponto de entrada _start. A função global _start é o ponto de entrada do programa, onde a execução começa. O linker procura a função _start para saber onde começar a execução do programa.

O "_start:" é uma marcação de rótulo que indica o início da função. Ela é usada como referência em outras partes do programa. No exemplo acima, a função _start começa com a instrução "mov eax, 4", que envia uma chamada de sistema para escrever no terminal a mensagem "Hello, world!".

Agora com esse conhecimento, vamos compilar o nosso programa.

## Compilando e executando o programa

Salve o arquivo e feche o editor de texto. Abra um terminal e navegue até o diretório onde o arquivo .asm foi salvo.

Compile o arquivo com o seguinte comando:

```
nasm -f elf64 -o hello.o hello.asm
``` 
Esse comando usa o nasm, um compilador de Assembly, para gerar um arquivo objeto (.o) a partir do código-fonte Assembly.

Link o arquivo objeto com o seguinte comando:
``` 
ld -o hello hello.o
```

Esse comando usa o ld, um linker, para gerar um executável chamado "hello" a partir do arquivo objeto gerado na etapa anterior.

Execute o programa com o seguinte comando:
```bash
./hello
```
O programa deve imprimir "Hello, world!" na tela.

## Alguns exemplos de instruções assembly

Exemplos de códigos Assembly x86_64:
Aqui estão alguns exemplos simples de códigos Assembly x86_64 que mostram como as instruções são escritas:

### Movendo valores entre registradores:

```asm
movq %rax, %rbx
``` 

### Adicionando dois valores:

```asm
addq %rbx, %rax
```

### Pulando para outra parte do código:

```
jmp label
...
label:
``` 
As principais instruções do Assembly x86_64:
Aqui estão algumas das principais instruções do Assembly x86_64 que são usadas com frequência:

- Mov: move um valor de um registrador ou de uma memória para outro registrador ou memória.
- Add/sub: adiciona ou subtrai valores de registradores ou de memória.
- Jmp: pula para outra parte do código.
- Cmp: compara dois valores e define a flag de condição com base no resultado.
- Jz: salta para outra parte do código se a flag de condição ZF for verdadeira.
- Jne: salta para outra parte do código se a flag de condição ZF for falsa.
- Call: chama uma função em outro lugar no código.
- Ret: retorna de uma função para onde foi chamada.

## Conclusão:
A linguagem Assembly x86_64 é uma linguagem de baixo nível que permite escrever programas diretamente em linguagem de máquina. Embora seja mais difícil de ler e escrever do que as linguagens de alto nível, ela pode ser muito eficiente e poderosa em alguns casos. Saber programar em Assembly x86_64 é uma habilidade valiosa para aqueles que trabalham com baixo nível de programação.

## Links úteis

- [Assembly Language in 100 Seconds](https://youtu.be/4gwYkEK0gOk)
