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



