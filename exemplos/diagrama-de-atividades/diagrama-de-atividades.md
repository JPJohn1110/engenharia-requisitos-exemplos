# Diagrama de Atividades

O Diagrama de Atividades é uma ferramenta de modelagem visual usada para representar o fluxo de atividades e processos em um sistema. É amplamente utilizado em engenharia de software para descrever os comportamentos dinâmicos e a sequência de ações que ocorrem dentro de um sistema ou processo.

## Objetivo

O objetivo principal do Diagrama de Atividades é ilustrar como as atividades são realizadas e como elas se conectam dentro de um fluxo de trabalho. Ele ajuda a identificar a sequência de operações e a lógica envolvida, facilitando a compreensão dos processos e a detecção de possíveis melhorias.

## Componentes Principais

1. **Atividades**: Representam ações ou tarefas executadas no sistema. Cada atividade é representada por um retângulo com bordas arredondadas.
2. **Fluxos de Controle**: Indicam a ordem de execução das atividades. São representados por setas que conectam as atividades.
3. **Decisões**: Pontos onde o fluxo pode seguir diferentes caminhos com base em condições específicas. São representados por losangos.
4. **Entradas e Saídas**: Representam dados ou objetos que entram ou saem do fluxo de atividades. São geralmente representados por setas ou objetos.
5. **Pontos de Início e Fim**: Indicam o início e o término do fluxo de atividades. O início é representado por um círculo sólido, e o fim por um círculo com um anel ao redor.
6. **Forks e Joins**: Utilizados para representar a divisão e a convergência de fluxos paralelos de atividades. Forks (bifurcações) são representados por linhas horizontais ou verticais, e joins (uniões) por linhas que convergem.

## Exemplo de Diagrama de Atividades

Aqui está um exemplo simples de um Diagrama de Atividades que ilustra o processo de aprovação de um pedido:

1. **Início**: O processo começa quando um pedido é recebido.
2. **Verificar Pedido**: O pedido é verificado quanto à disponibilidade de estoque.
3. **Decisão**: Se o item está em estoque, o pedido é aprovado; caso contrário, é rejeitado.
4. **Atualizar Estoque**: Após a aprovação, o estoque é atualizado.
5. **Enviar Confirmação**: Uma confirmação de pedido é enviada ao cliente.
6. **Fim**: O processo é concluído.

```plaintext
[Início] → [Verificar Pedido] 
          → [Decisão] → [Item em Estoque] → [Atualizar Estoque] → [Enviar Confirmação] → [Fim]
                     ↓ 
                [Item Fora de Estoque] → [Cancelar Pedido] → [Enviar Notificação] → [Fim]
