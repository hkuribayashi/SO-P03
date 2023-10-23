# Laboratório de Sistemas Operacionais para estudo de Processos e Prioridades (SO-P03)

Este projeto é uma demonstração reproduzível do conceito de prioridades de processos em sistemas operacionais Linux.

Este projeto é para alunos da disciplina SI01021 (Sistemas Operacionais) do Curso de Sistemas de Informação da Unifesspa, que querem testar ferramentas para ajuste de prioridades de processos em Sistemas Linux.

## O que é Prioridade? 

Prioridade é uma medida de privilégio que algo ou alguém possui. Todo processo no Linux possui prioridades de CPU, Memória e Disco. Alguns possuem mais prioridades do que outros, ou seja, mais ou menos privilégios no consumo desses recursos.

Apesar do sistema determinar a prioridade padrão de cada processo, podemos especificar a quais processos queremos aplicar mais ou menos privilégios. Para isso, usamos os comandos nice e renice.

Veremos, a seguir, quando e como utilizar cada um deles.

## Conceituando a syntaxe dos comandos nice e renice

Antes de começarmos, é interessante entendermos um conceito: O termo “nice” em inglês significa “legal“. Um processo “legal” para a CPU é aquele que não demanda maior prioridade.

A syntax dos comandos nice e renice são acompanhadas por números que vão de -20 à +20, onde “-20” significa menos legal, e “+20” significa “mais legal“. 

Um processo -20 tem maior prioridade, por isso é menos legal. Já o +20 é bem legal, e por isso tem menos prioridade.

### Comando nice

O comando nice nos permite especificar a prioridade de CPU e Memória com a qual um processo será iniciado. Ou seja, o processo iniciará com a prioridade que especificarmos e manterá essa prioridade até que seja finalizado.

O comando para isso seria:

Podemos recuperar o cabeçalho deste arquivo fazendo:

    $ head -n 3 Tux.ppm
    P6
    265 314
    255
