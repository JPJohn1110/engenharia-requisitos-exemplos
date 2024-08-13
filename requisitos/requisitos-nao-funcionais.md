# Requisitos Não Funcionais

Requisitos não funcionais especificam atributos de qualidade e restrições do sistema, como desempenho, usabilidade e segurança.

## Exemplo de Requisito Não Funcional

- **ID**: RNF001
- **Descrição**: O sistema deve suportar até 1000 transações por segundo.
- **Critérios de Aceitação**:
  1. O sistema deve ser testado com uma carga de 1000 transações por segundo e manter um tempo de resposta inferior a 2 segundos.
  2. A interface deve ser intuitiva e fácil de usar, com um tempo de aprendizado para novos usuários não superior a 15 minutos.
  
  ### RNF001 - Performance
- **Descrição**: O sistema deve ser capaz de suportar até 1000 usuários simultâneos.
- **Critérios de Aceitação**:
  - O sistema deve manter um tempo de resposta abaixo de 2 segundos durante picos de carga.

### RNF002 - Segurança
- **Descrição**: O sistema deve criptografar as senhas dos usuários no banco de dados.
- **Critérios de Aceitação**:
  - As senhas devem ser armazenadas usando um algoritmo de criptografia seguro (por exemplo, bcrypt).
  - As senhas não devem ser armazenadas em texto simples.

## Observações

- **Documentação**: Mantenha os requisitos atualizados e documentados de forma clara para garantir que todas as partes interessadas estejam alinhadas.
- **Revisões**: Reavalie e revise os requisitos regularmente para ajustar às mudanças de escopo e necessidades dos usuários.

