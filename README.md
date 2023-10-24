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

O comando nice tem a seguinte estrutura:

    $ nice -n prioridade comando

Desta forma, temos o seguinte exemplo:

    $ nice -n 12 firefox

No exemplo acima, o comando firefox será executado com prioridade “12“. Ao consultar novamente os processo disponíveis com o comando 'ps -efdl', temos:

![Imagem1](/Imagem1.png)

### Comando renice

O comando renice é similar ao nice. A diferença entre eles é que o renice é utilizado em processos que já estão em execução.

A syntax dele é esta:

    $ renice -10 -p PID

Desta forma, temos o seguinte exemplo:

    $ renice -10 -p 25876

Desta forma, o processo cujo PID é 25876 passará para prioridade “-10“. Observe que é preciso ter o número do PID para trocarmos a prioridade do processo.

Caso queiramos trocar a prioridade dos processos de um determinado usuário, podemos utilizar o parâmetro “-u” e especificarmos esse usuário. Exemplo:

    $ renice -10 -u usuario

Com isso, todos processos desse usuário passarão para prioridade “-10“.

## Conclusão

Como dito anteriormente, o Linux gerencia a prioridade de processos da forma como ele, Linux, considera ser melhor para o sistema. Acontece que, as vezes, o melhor para o sistema não é melhor para nós, então a troca da prioridade de um processo se faz necessária. Com esses 3 comandos, como vimos anteriormente, podará gerenciar prioridades como bem entender. Só tome cuidado para não gerar sobrecargas desnecessárias.

## Referências

LinuxZilla, 2023. Disponível em: https://www.linuxzilla.com.br/2022/04/17/linux-gerenciando-prioridades-de-processos/


