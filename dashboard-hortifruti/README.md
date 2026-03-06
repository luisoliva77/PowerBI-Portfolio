# 📊 Dashboard de Vendas – Hortifruti

## 📌 Sobre o Projeto

Este projeto foi desenvolvido com o objetivo de simular o funcionamento de um sistema de vendas para um **hortifruti**, desde a modelagem do banco de dados até a criação de um **dashboard analítico no Power BI**.

O projeto contempla:

* Modelagem relacional do banco de dados
* Criação de procedures para registro de vendas
* Controle de movimentação de estoque
* Criação de views para análise de dados
* Construção de um dashboard interativo no Power BI

A ideia principal foi transformar **dados operacionais de vendas em informações estratégicas**, permitindo a análise de desempenho do negócio.

---

# 🗄️ Estrutura do Banco de Dados

O banco foi modelado para representar o fluxo completo de vendas de um hortifruti.

## Principais Entidades

### 🛒 Vendas

Armazena informações gerais das vendas realizadas.

Campos principais:

* ID da venda
* Cliente
* Vendedor
* Forma de pagamento
* Data da venda

---

### 📦 Itens da Venda

Tabela responsável por armazenar os produtos vendidos em cada venda.

Campos principais:

* Produto
* Quantidade vendida
* Preço unitário
* Venda associada

Essa tabela permite calcular métricas como:

* Faturamento
* Quantidade vendida
* Ticket médio

---

### 🥬 Produtos

Contém os produtos comercializados pelo hortifruti.

Relacionamentos com:

* Categoria
* Fornecedor
* Movimentação de estoque

---

### 🏷️ Categorias

Classificação dos produtos (exemplo):

* Frutas
* Verduras
* Legumes
* Hortaliças

---

### 🚚 Fornecedores

Representa as empresas responsáveis por fornecer os produtos vendidos.

---

### 👨‍💼 Vendedores

Tabela responsável por identificar os vendedores responsáveis pelas vendas.

---

### 👥 Clientes

Armazena os clientes que realizaram compras.

---

### 💳 Forma de Pagamento

Registra os métodos de pagamento utilizados nas vendas:

* Pix
* Dinheiro
* Cartão de crédito
* Cartão de débito

# 📊 Views para Análise

Para facilitar a integração com o Power BI, foram criada uma view analítica.

## VW_FATURAMENTO_ITEM

View mais detalhada contendo:

* Produto
* Categoria
* Fornecedor
* Quantidade vendida
* Valor total do item
* Cliente
* Vendedor
* Forma de pagamento
* Data da venda

Essa view foi utilizada como **base principal para o Power BI**.

---

# 📈 Dashboard Power BI

O dashboard foi criado com o objetivo de transformar os dados em **insights de negócio**.

## Indicadores principais

* 💰 **Faturamento Total**
* 🧾 **Ticket Médio**
* 📦 **Quantidade Vendida**
* 👥 **Clientes Atendidos**

---

## Visualizações criadas

### 📈 Faturamento por mês

Gráfico de linha mostrando evolução das vendas ao longo do ano.

### 🍎 Produtos mais vendidos

Ranking dos produtos com maior volume de vendas.

### 💳 Faturamento por forma de pagamento

Gráfico de rosca mostrando distribuição dos pagamentos.

### 🏢 Análise por fornecedor

Análise de faturamento gerado por cada fornecedor.

### 🥦 Hierarquia de produtos

Visualização hierárquica:

Fornecedor → Categoria → Produto

---

# 🎯 Objetivos do Projeto

Este projeto teve como objetivo praticar:

* Modelagem de banco de dados
* SQL Server
* Procedures
* Triggers
* Views analíticas
* Integração com Power BI
* Criação de dashboards analíticos

---

# 🛠️ Tecnologias Utilizadas

* **SQL Server**
* **T-SQL**
* **Power BI**
* **Git / GitHub**

---

# 📷 Exemplo do Dashboard

O dashboard apresenta indicadores de desempenho e análises visuais para auxiliar na tomada de decisão.

Entre os insights possíveis:

* Produtos mais vendidos
* Melhor vendedor
* Forma de pagamento mais utilizada
* Evolução de faturamento ao longo do tempo
* Desempenho por fornecedor

---

# 👨‍💻 Autor

Projeto desenvolvido por **Luís Felipe** como prática de modelagem de dados, SQL e análise de dados com Power BI.
