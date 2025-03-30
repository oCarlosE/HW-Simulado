# Projeto de Hardware Simulado para Sistemas Operacionais
Este repositório é dedicado à criação de um hardware simulado para a disciplina de sistemas operacionais, utilizando um código base fornecido pelo professor.

Objetivos da Primeira Etapa do Trabalho:

- Desenvolvimento de um gerenciador de memória paginada.

- Implementação de um gerenciador de processos.

- Elaboração de um escalonamento contínuo de processos.

Estas são as principais tarefas a serem completadas na primeira fase do projeto.

# Gerenciador de Memória:
O Gerente de Memória (GM) é responsável por alocar e desalocar memória para os processos do sistema, garantindo que cada processo tenha um espaço adequado na memória RAM.

Ele usa um esquema de paginação, ou seja, divide a memória em frames e os processos em páginas. Cada página de um processo pode ser alocada em qualquer frame livre da memória.

## Atributos e métodos necessários
    - Um vetor para representar a memória
    - Um inteiro para definir o tamanho das páginas
    - Um inteiro para o número total de frames na memória
    - Uma tabela de páginas para controlar quais frames estão livres e quais estão ocupados
    - Um array para armazenar os frames alocados para um processo
    - Método para buscar frames disponíveis
    - Método para alocar memória para um processo
    - Método para desalocar memória para um processo


