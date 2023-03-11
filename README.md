## Atenção ⚠️! 

A grande maioria dessas aulas ainda não estão prontas, e algumas precisam de passar por algumas revisões antes que possam ser usadas
para ensino. Por conta disso, olhe o conteúdo desse repositório com cuidado. Se você puder contribuir de alguma forma para esse repositório,
eu ficaria muito agradecido.

# Microfundamentos de Compiladores

Essa disciplina tem a fama de ser bem difícil e as vezes pode ser difícil encontrar material bom
na internet que consiga explicar bem o conteúdo. Por esse motivo, decidi criar esse repositório para 
agrupar todos os materiais pertinentes para o aprendizado da disciplina, desde a fundamentação em FTC(Fundamentos
Teóricos da Computação), até a Geração de Código em Assembly.

Pense nesse repositório como apenas um lugar para auxiliar nos seus estudos. 

Também não se esqueçam de olhar as referência bibliográficas sugeridas pelo seu professor. mas caso alguns de vocês queiram as minhas referências para a disciplina, fica ai as minhas indicações:
- [Compiladores: Princípios, Técnicas e Ferramentas](https://www.amazon.com.br/Compiladores-Princ%C3%ADpios-T%C3%A9cnicas-Alfred-Aho/dp/8521610572) (Mais completo de todos. Bom para ver teoria e prática)
- [Playlist de Compiladores do Canal "Aulas de Computação"](https://youtube.com/playlist?list=PL0Z-gyL9saMcajYH26KWKQG0nH2C2fsMQ) (Bom para ver a teoria, além de ter exercícios explicados)
- [Playlist de Compiladores do Professor Judson Santiago](https://www.youtube.com/playlist?list=PLX6Nyaq0ebfhI396WlWN6WlBm-tp7vDtV) (Alem de ter teoria, possui também exemplos de código)
- [Slides de Compiladores da UFMG](https://homepages.dcc.ufmg.br/~bigonha/Cursos/comp-slides-p4.pdf) (Slides da professora Mariza A S. Bigonha, teoria e prática muito bem explicada e com vários exemplos com imagens).

Se você quiser contribuir para esse repositório, dê uma olhada depois no arquivo COMO-CONTRIBUIR.md

Muito obrigado e um ótimo dia para todos! :)

# Sumário

* [COMO CONTRIBUIR](CONTRIBUIR.md)
* [Microfundamentos Compiladores](README.md)
* [FTC](FTC/README.md)
  * [Autômato finito determinístico](FTC/Automatos/README.md)
  * [Expressões regulares](FTC/Expressoes-regulares/README.md)
  * [Gramáticas](FTC/Gramaticas/README.md)
    * [Gramática LL(1)](FTC/Gramaticas/gramatica-ll1.md)
    * [Expressões regulares juntos as gramáticas](FTC/Gramaticas/expressoes-regulares-em-gramaticas.md)
* [Introdução a Compiladores - conceitos principais e primeiros passos](Introducao/README.md)
  * [Visão geral e conceitos principais](Introducao/Visao-geral-e-conceitos-principais.md)
  * [Definindo a linguagem que queremos criar](Introducao/Definindo-a-linguagem-que-queremos-criar.md)
  * [Criando a base do Compilador](Introducao/Criando-a-base-do-Compilador.md)
* [Front-End - Fase da Vanguarda e Tabela de Símbolos](Front-End/README.md)
  * [Tabela de Simbolos](Front-End/Tabela-de-Simbolos/README.md)
    * [Teoria](Front-End/Tabela-de-Simbolos/Teoria.md)
    * [Implementação](Front-End/Tabela-de-Simbolos/Implementacao.md)
  * [Analisador Léxico](Front-End/Analisador-Lexico/README.md)
    * [Teoria](Front-End/Analisador-Lexico/Teoria.md)
    * [Implementação](Front-End/Analisador-Lexico/Implementacao.md)
  * [Analisador Sintático](Front-End/Analisador-Sintatico/README.md)
    * [Teoria](Front-End/Analisador-Sintatico/Teoria.md)
    * [Implementação](Front-End/Analisador-Sintatico/Implementacao.md)
  * [Analisador Semântico](Front-End/Analisador-Semantico/README.md)
    * [Teoria](Front-End/Analisador-Semantico/Teoria.md)
    * [Implementação](Front-End/Analisador-Semantico/Implementacao.md)
* [Middle-End - Geração de Código intermediário e Otimização](Middle-End/README.md)
  * [Geração de Código Intermediário](Middle-End/Geracao-de-Codigo-Intermediario/README.md)
    * [Teoria](Middle-End/Geracao-de-Codigo-Intermediario/Teoria.md)
    * [Implementação](Middle-End/Geracao-de-Codigo-Intermediario/Implementacao.md)
  * [Otimização de Código](Middle-End/Otimizacao-de-Codigo/README.md)
    * [Teoria](Middle-End/Otimizacao-de-Codigo/Teoria.md)
    * [Implementação](Middle-End/Otimizacao-de-Codigo/Implementacao.md)
* [Back-End - Geração de Código Assembly e Ambientes em Tempo de Execução](Back-End/README.md)
  * [Geração de Código](Back-End/Geracao-de-Codigo/README.md)
    * [Teoria](Back-End/Geracao-de-Codigo/Teoria.md)
    * [Implementação](Back-end/geracao-de-codigo/implementacao.md)
  * [Ambientes em Tempo de Execução](Back-End/Ambientes-em-tempo-de-execucao/README.md)
    * [Teoria](Back-End/Ambientes-em-tempo-de-execucao/Teoria.md)
