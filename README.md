# Projeto de Hardware Simulado para Sistemas Operacionais
Este repositório é dedicado à criação de um hardware simulado para a disciplina de sistemas operacionais, utilizando um código base fornecido pelo professor.

### Objetivos da Primeira Etapa do Trabalho:

- Desenvolvimento de um gerenciador de memória paginada.

- Implementação de um gerenciador de processos.

- Elaboração de um escalonamento contínuo de processos.

Estas são as principais tarefas a serem completadas na primeira fase do projeto.

# Gerenciador de Memória:
O Gerente de Memória (GM) é responsável por alocar e desalocar memória para os processos do sistema, garantindo que cada processo tenha um espaço adequado na memória RAM.

Ele usa um esquema de paginação, ou seja, divide a memória em frames e os processos em páginas. Cada página de um processo pode ser alocada em qualquer frame livre da memória.

### Atributos e métodos necessários
    - Um vetor para representar a memória
    - Um inteiro para definir o tamanho das páginas
    - Um inteiro para o número total de frames na memória
    - Uma tabela de páginas para controlar quais frames estão livres e quais estão ocupados
    - Um array para armazenar os frames alocados para um processo
    - Método para buscar frames disponíveis
    - Método para alocar memória para um processo
    - Método para desalocar memória para um processo

# Gerenciador de Processos:

O Gerente de Processos (GP) é responsável por criar, gerenciar e finalizar os processos do sistema. Ele mantém informações sobre cada processo através do PCB (Process Control Block), que armazena o estado de cada processo, seus registradores e outras informações essenciais.

### Atributos e métodos necessários
    PCB: 
    - Um inteiro para identificar o processo
    - Um inteiro para ser o Program Counter (PC)
    - Um array de registradores para salvar valores utilizados nos processos
    - Uma objeto para definir o estado do processo
    - Um array para as armazenar páginas da memória alocadas para este processo
    
    GP: 
    - Uma lista para armazenar os processos
    - Um inteiro para manter controle do próximo ID a ser atribuído a um processo]
    - Método para criar um novo processo
    - Método para mudar o estado do processo
    - Método para finalizar um processo

# Escanolador

O escalonador gerencia a execução dos processos na CPU, decidindo qual processo será executado em cada momento. Ele alterna entre processos para garantir uso eficiente do processador, equilibrando tempo de resposta e desempenho do sistema.

    - Uma fila (Queue) para armazenar processos prontos
    - Um inteiro para o ID do processo atual
    - Método para adicionar processos na fila
    - Método para escolher o próximo processo
    - Método para salvar os registradores e o PC do processo atual
    - Método para restaurar os valores dos registradores e do PC do novo processo a ser executado
    - Método para executar processos

# Fluxo de execução do programa

### Inicialização do Sistema
    1.1 Criação da memória principal como um vetor de palavras (Word[] m).  
    1.2 Definição do tamanho das páginas e frames.  
    1.3 Criação da tabela de páginas para rastrear os frames livres.  
    1.4 Inicialização do Gerente de Processos (GP) para gerenciar os processos.  
    1.5 Inicialização do Escalonador para definir qual processo será executado.  

### Criação de um Novo Processo
    2.1 O Gerente de Memória (GM) verifica se há espaço suficiente na RAM.
    2.2 O código do programa é dividido em páginas e os frames livres são alocados.
    2.3 As instruções do programa são carregadas nos frames disponíveis.
    2.4 O Gerente de Processos (GP) cria um PCB (Process Control Block).
    2.5 O estado do processo é definido como "PRONTO".
    2.6 O processo é adicionado à fila do escalonador.

### Escalonamento e Seleção do Processo
    3.1 O escalonador escolhe um processo da fila de prontos.
    3.2 O estado do processo selecionado é alterado para "EXECUTANDO".
    3.3 Os registradores e o contador de programa (PC) do processo anterior são salvos.
    3.4 O contexto do novo processo é carregado na CPU.

### Execução do Processo
    4.1 A CPU busca a próxima instrução do processo na memória.
    4.2 A CPU executa a instrução.
    4.3 O contador de programa (PC) é incrementado.
    4.4 Se o processo precisar esperar um recurso, ele é bloqueado e outro processo é escalonado.

### Troca de Contexto (Se Necessário)
    5.1 O estado do processo atual é salvo.
    5.2 O processo atual é colocado de volta na fila de prontos.
    5.3 O escalonador escolhe o próximo processo pronto para execução.
    5.4 O estado do novo processo é restaurado na CPU.

### Finalização do Processo
    6.1 O processo executa sua última instrução e seu estado muda para "FINALIZADO".
    6.2 O Gerente de Memória libera os frames usados pelo processo.
    6.3 O Gerente de Processos remove o PCB da lista de processos ativos.

### Repetição do Ciclo
    7.1 O escalonador seleciona outro processo da fila de prontos.
    7.2 O ciclo de execução continua enquanto houver processos ativos no sistema.

# Links úteis para o projeto

[MarkDown Guide](https://www.markdownguide.org/basic-syntax/) - Para escrever o README

[GM](https://www.dcce.ibilce.unesp.br/~aleardo/cursos/fsc/cap12.php) - Sobre Gerenciamento de memória

[GP](https://blog.grancursosonline.com.br/sistemas-operacionais-gerenciamento-de-processos/) - Sobre Gerenciamento de processos

[PCB](https://www.geeksforgeeks.org/process-table-and-process-control-block-pcb/) - Sobre Process Control Block

[PG](https://www.inf.pucrs.br/~emoreno/undergraduate/CC/sisop/class_files/Aula11.pdf) - Sobre Tabela de Páginas



