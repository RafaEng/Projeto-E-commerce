# Modelo Conceitual de E-commerce

Este diagrama representa o modelo conceitual de um sistema de e-commerce, modelado utilizando o Modelo Entidade-Relacionamento (MER). O objetivo é ilustrar as principais entidades e seus relacionamentos dentro do sistema, abrangendo funcionalidades como gestão de produtos, fornecedores, clientes, pedidos, pagamentos e entregas.

![Modelo Conceitual de E-commerce](modelo_conceitual.png)

## Entidades Principais:

* **Fornecedor:** Representa as empresas que fornecem os produtos.
* **Terceiro:** Representa vendedores terceirizados que também oferecem produtos.
* **Cliente:** Representa os usuários que realizam compras no sistema, podendo ser Pessoa Física (PF) ou Pessoa Jurídica (PJ). A distinção entre PJ e PF é feita através do atributo `Tipo Conta`, e o atributo `Identificação` armazena o CPF ou CNPJ correspondente.
* **Produto:** Representa os itens à venda no sistema.
* **Estoque:** Representa os locais onde os produtos estão armazenados.
* **Pedido:** Representa as ordens de compra realizadas pelos clientes.
* **Pagamento:** Representa as diferentes formas de pagamento que um cliente pode utilizar. Um cliente pode ter múltiplas formas de pagamento cadastradas.
* **Entrega:** Representa o processo de envio de um pedido, contendo informações sobre o status e o código de rastreio.
* **Produto no Estoque:** Representa a quantidade de um determinado produto em um determinado local de estoque.
* **Disponibiliza um Produto:** Representa a relação entre fornecedores e os produtos que eles disponibilizam.
* **Produtos por Vendedor:** Representa a relação entre vendedores terceirizados e os produtos que eles oferecem.
* **Relação Produto/Pedido:** Representa os itens individuais que compõem um pedido.
* **Cliente_has_Pagamento:** Representa a relação entre clientes e suas formas de pagamento cadastradas.

## Relacionamentos Principais:

* Um Fornecedor pode disponibilizar muitos Produtos (`1:*`).
* Um Terceiro pode oferecer muitos Produtos (`1:*`).
* Um Cliente realiza muitos Pedidos (`1:*`).
* Um Pedido contém muitos Produtos (`1:*`, através da entidade associativa `Relação Produto/Pedido`).
* Um Produto está presente em muitos Pedidos (`1:*`, através da entidade associativa `Relação Produto/Pedido`).
* Um Produto pode estar em muitos Estoques (`1:*`, através da entidade associativa `Produto no Estoque`).
* Um Estoque pode conter muitos Produtos (`1:*`, através da entidade associativa `Produto no Estoque`).
* Um Cliente pode ter muitas formas de Pagamento cadastradas (`1:*`).
* Uma forma de Pagamento pode ser utilizada por muitos Clientes (`1:*`).
* Um Pedido possui uma Entrega (`1:1`).

## Refinamentos do Modelo:

* **Gestão de Clientes (PF/PJ):** O modelo foi estruturado para acomodar as informações específicas de clientes Pessoa Física e Pessoa Jurídica, garantindo a integridade dos dados e evitando ambiguidades no cadastro.
* **Processamento de Pagamentos:** A flexibilidade para que clientes utilizem diversas formas de pagamento foi incorporada através de um relacionamento muitos para muitos, permitindo uma experiência de compra mais abrangente.
* **Rastreamento de Entregas:** A inclusão da entidade `Entrega` com seus atributos essenciais permite o acompanhamento logístico dos pedidos, fornecendo informações cruciais tanto para o cliente quanto para a administração do sistema.
