# Entendendo a Geração de Código

## Geração de código

A geração de código é última e uma das etapas principais do processo de compilação em um compilador. Na etapa passada vocês viram como que podemos criar uma representação intermediária do código usando o Middle-End com os dados extraídos do código fonte pelo Front-End. Além disso, vocês viram como que podemos pegar essa representação de código intermediário e otimizá-la, agora, na geração de código, vamos pegar esse resultado final do Middle-End e transformar em código que possa ser executado pelo procesador ou uma máquina virtual.

A geração de código é uma etapa crítica do processo de compilação, pois o código gerado precisa ser eficiente, correto e capaz de executar todas as operações especificadas no código-fonte do programa. A eficiência é importante para garantir que o programa execute em um tempo razoável e use a menor quantidade de memória possível. A correção é essencial para garantir que o programa execute corretamente, sem erros ou comportamentos inesperados. A capacidade de executar todas as operações especificadas no código-fonte é necessária para garantir que o programa faça o que foi projetado para fazer.

## Assembly

Código assembly é uma linguagem de baixo nível que é compreendida pelos processadores. É uma representação textual do código de máquina que um processador pode executar diretamente. Cada instrução em código assembly é traduzida para uma ou mais instruções de código de máquina, que são executadas diretamente pelo processador.

A geração de código assembly é realizada pela última fase do compilador, após a análise semântica e a geração de código intermediário. O objetivo dessa fase é traduzir o código intermediário em código assembly, que é mais próximo da linguagem de máquina.

A geração de código assembly geralmente é feita em duas etapas principais:

### Alocação de registradores: 

o primeiro passo é alocar registradores para as variáveis do programa. Os registradores são espaços de memória de alta velocidade dentro do processador que podem ser usados para armazenar valores temporários. A alocação de registradores é importante para garantir que o programa execute de maneira eficiente e use a menor quantidade de memória possível.

### Geração de código: 

o segundo passo é gerar o código assembly real a partir do código intermediário. Cada instrução do código intermediário é traduzida em uma ou mais instruções de código assembly que são executadas diretamente pelo processador. Essas instruções são escritas em um arquivo de saída em formato de texto que pode ser lido pelo montador.

Exemplo:
Vamos considerar o seguinte código em C:

```c
int main() {
  int a = 5;
  int b = 10;
  int c = a + b;
  return c;
}
```

Depois da análise léxica, sintática e semântica, o compilador gera o seguinte código intermediário:

```asm
t1 = 5
t2 = 10
t3 = t1 + t2
return t3
```

Finalmente, a geração de código assembly produz o seguinte código:

```asm
.section .data
.section .text
.globl main
main:
  pushl %ebp
  movl %esp, %ebp
  subl $8, %esp
  movl $5, -4(%ebp)
  movl $10, -8(%ebp)
  movl -4(%ebp), %eax
  addl -8(%ebp), %eax
  movl %eax, -12(%ebp)
  movl -12(%ebp), %eax
  leave
  ret
```

Neste exemplo, o código assembly começa com a rotina "main:", que inicializa o frame de ativação da função. Em seguida, o código assembly aloca espaço na pilha para as variáveis "a", "b" e "c". Depois, o código assembly carrega os valores das variáveis "a" e "b" em registradores, realiza a operação de adição e armazena o resultado na variável "c". Finalmente, o código assembly carrega o valor de "c" em um registrador
