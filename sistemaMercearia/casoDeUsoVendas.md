# Casos de Uso do Sistema de Mercearia

## UC01: Realizar Venda

### Ator(es):
* **Cliente:** Realiza a compra e o pagamento dos produtos.
* **Operadora de pagamentos:** Processa as transações eletrônicas (débito, crédito, Pix e vale refeição).
* **Funcionário do caixa:** Registra os itens, finaliza a venda e recebe o pagamento.

### Interessado(s) e Interesse(s):
* **Cliente:** Deseja realizar a compra de forma eficiente e com opções de pagamento flexíveis.
* **Funcionário do caixa:** Quer realizar a venda corretamente, sem erros no registro dos itens e valores.
* **Proprietário da mercearia:** Deseja que as vendas sejam bem registradas, o estoque atualizado e o pagamento processado corretamente.
* **Operadora de pagamentos:** Assegura que as transações financeiras sejam seguras e processadas corretamente.

### Pré-condições:
* O sistema de PDV deve estar em funcionamento e conectado à operadora de pagamentos.
* O cliente já escolheu os produtos que deseja comprar.
* O sistema está com o estoque e preços atualizados.

### Pós-condições:
* A venda foi registrada e o estoque atualizado.
* O pagamento foi concluído e registrado.
* Um comprovante da venda foi gerado e entregue ao cliente.

### Fluxo Principal:

1. **O cliente escolhe os produtos e leva ao caixa.**

2. **[IN] O funcionário registra os itens.**
   - O sistema exibe o preço de cada item e aplica descontos ou promoções quando houver.

3. **[OUT] O sistema exibe o valor total da compra.**

4. **[IN] O funcionário finaliza a venda.**

5. **[OUT] O sistema informa as formas de pagamento.**

6. **[IN] O cliente escolhe a forma e realiza o pagamento.**
   - O cliente escolhe entre dinheiro, cartão de débito, cartão de crédito, Pix ou vale refeição.

   ### 6.1 Pagamento com Dinheiro
   6.1.1. O cliente entrega o dinheiro ao funcionário.  
   6.1.2. O sistema calcula o troco e o funcionário entrega ao cliente.

   ### 6.2 Pagamento com Cartão de Débito
   6.2.1. O cliente insere o cartão no terminal.  
   6.2.2. O sistema envia a transação para a operadora de pagamentos e, após autorização, a venda é concluída.

   ### 6.3 Pagamento com Cartão de Crédito
   6.3.1. O cliente insere o cartão no terminal.  
   6.3.2. O sistema oferece as opções de parcelamento.  
   6.3.3. A operadora autoriza o pagamento e a venda é concluída.

   ### 6.4 Pagamento com Pix
   6.4.1. O sistema gera um QR Code ou chave Pix.  
   6.4.2. O cliente realiza o pagamento e a operadora autoriza a transação.

   ### 6.5 Pagamento com Vale Refeição
   6.5.1. O cliente insere o cartão no terminal.  
   6.5.2. O sistema envia os dados para a operadora de vale refeição, que autoriza a transação.

7. **[OUT] O funcionário confirma o pagamento e entrega o comprovante ao cliente.**

### Fluxos Alternativos:

### FA01: Venda Cancelada
   1. O cliente decide não prosseguir com a compra após o registro dos itens.
   2. O funcionário cancela a venda no sistema.
   3. O sistema reverte qualquer ajuste no estoque e limpa os itens registrados.

### Exceções:
* **Falha na autorização de pagamento:**  
   - O sistema exibe um erro e solicita que o cliente tente novamente ou escolha outro meio de pagamento.
   
* **Valor insuficiente em dinheiro:**  
   - O sistema avisa que o valor fornecido não cobre o total e o funcionário solicita mais dinheiro ou outra forma de pagamento.

---

## UC02: Cancelar Venda

### Ator(es):
* **Funcionário do caixa:** Cancela a venda antes de ser finalizada.
* **Cliente:** Pode solicitar o cancelamento da compra antes de concluir o pagamento.

### Interessado(s) e Interesse(s):
* **Funcionário do caixa:** Deseja corrigir erros na venda ou atender a solicitação do cliente para cancelar a compra.
* **Cliente:** Deseja cancelar a compra, seja por mudança de decisão ou erro.

### Pré-condições:
* A venda ainda não foi finalizada, ou seja, o pagamento não foi processado.
* Os itens já foram registrados, mas o cliente não efetuou o pagamento.

### Pós-condições:
* A venda é cancelada e o sistema reverte todas as operações relacionadas.
* O estoque é atualizado, revertendo as reservas feitas durante o registro dos produtos.

### Fluxo Principal:

1. **O cliente solicita o cancelamento da venda.**
   
2. **[IN] O funcionário seleciona a opção de cancelar a venda no sistema.**

3. **[OUT] O sistema remove os itens registrados da lista de compra.**
   - O estoque dos itens é restaurado.

4. **[OUT] O sistema cancela a transação e retorna ao estado inicial.**
   - Nenhum pagamento é registrado.

### Fluxos Alternativos:

### FA01: Venda parcialmente registrada
   - Se apenas alguns dos itens foram registrados, o sistema permite que o funcionário remova os itens individualmente, sem cancelar a venda por completo.

### Exceções:
* **Venda já finalizada:**  
   - Se o pagamento já foi concluído, a venda não pode ser cancelada. O sistema sugere realizar uma devolução de produto.

---

## UC03: Devolver Produto

### Ator(es):
* **Cliente:** Solicita a devolução de um ou mais produtos após a compra.
* **Funcionário do caixa:** Registra a devolução no sistema e processa o reembolso ou crédito.

### Interessado(s) e Interesse(s):
* **Cliente:** Deseja devolver o produto, seja por arrependimento ou defeito.
* **Funcionário do caixa:** Deve processar a devolução e ajustar o estoque e o pagamento.
* **Proprietário da mercearia:** Quer garantir que o processo de devolução seja registrado corretamente, com ajuste do estoque e controle financeiro.

### Pré-condições:
* A venda original deve estar registrada no sistema.
* O produto deve estar em condições aceitáveis para devolução, conforme a política da mercearia.

### Pós-condições:
* O produto devolvido é removido do inventário de vendas e adicionado de volta ao estoque (se aplicável).
* O cliente recebe o reembolso ou crédito, conforme o método de pagamento original.

### Fluxo Principal:

1. **O cliente solicita a devolução do produto.**

2. **[IN] O funcionário localiza a venda original no sistema.**
   - O funcionário verifica se o produto está elegível para devolução, de acordo com a política da loja.

3. **[OUT] O sistema confirma a devolução e ajusta o estoque.**
   - O produto é removido do inventário de vendas e adicionado de volta ao estoque, se apropriado.

4. **[IN] O funcionário processa o reembolso ou crédito.**
   - O cliente pode receber o valor de volta em dinheiro, crédito na loja ou reversão no cartão de crédito/débito, dependendo da forma de pagamento original.

5. **[OUT] O sistema gera um comprovante da devolução e ajusta o relatório de vendas.**

### Fluxos Alternativos:

### FA01: Produto fora da política de devolução
   1. Se o produto não for elegível para devolução (por exemplo, alimentos perecíveis), o sistema exibe uma mensagem de erro e o funcionário informa ao cliente.

### Exceções:
* **Venda não encontrada:**  
   - Se a venda original não for encontrada no sistema, o funcionário deve solicitar um comprovante de compra ao cliente para proceder com a devolução.
   
* **Produto danificado ou fora da política de devolução:**  
   - O sistema bloqueia a devolução se o produto estiver fora das condições estabelecidas pela política da loja, como prazo excedido ou produto danificado.

---

# Relacionamentos entre os Casos de Uso
* **UC01: Realizar Venda** pode ser seguido por **UC03: Devolver Produto**, caso o cliente queira devolver um item após a compra.
* **UC02: Cancelar Venda** é um caso de uso que pode ocorrer durante **UC01: Realizar Venda** se o cliente decidir não comprar os produtos.
* **UC03: Devolver Produto** pode resultar em ajustes no estoque e no financeiro, afetando o relatório de vendas.

