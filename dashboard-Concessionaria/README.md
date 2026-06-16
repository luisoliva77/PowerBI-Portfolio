# AutoVendas - Dashboard e Banco de Dados para Gestão de Concessionária

## Sobre o Projeto

O AutoVendas é um projeto desenvolvido com o objetivo de simular um cenário real de gestão comercial em uma concessionária de veículos, integrando Banco de Dados SQL com análise de dados e visualização no Power BI.

O projeto foi construído de ponta a ponta, passando pela modelagem do banco de dados, automação de processos no SQL e construção de dashboards interativos para análise estratégica das vendas.

Este projeto teve como foco aplicar conhecimentos em SQL, modelagem de dados, automação com procedures e triggers, além de Business Intelligence com Power BI.

## Objetivo

Criar uma solução capaz de armazenar, processar e analisar informações de vendas de uma concessionária, permitindo acompanhar indicadores estratégicos e auxiliar na tomada de decisão.

### Tecnologias Utilizadas
SQL Server
Power BI
Procedures
Triggers

# Estrutura do Banco de Dados

## 2. Procedures para Automação

Foi criada uma Stored Procedure responsável por automatizar o processo de fechamento de vendas.

Funções da procedure:

Registrar a venda
Atualizar estoque
Validar disponibilidade do veículo
Registrar informações no banco

Exemplo:

CREATE PROCEDURE fechamento_venda (...)
BEGIN
   UPDATE estoque
   SET quantidade = quantidade - 1;

   INSERT INTO vendas (...);
END;

## 3. Trigger para Backup Automático

Implementação de uma Trigger responsável por realizar backup automático das vendas sempre que uma nova venda é registrada.

Objetivo:

Garantir segurança dos dados
Criar redundância
Automatizar auditoria de registros

Exemplo:

CREATE TRIGGER backup_vendas
AFTER INSERT ON vendas
FOR EACH ROW
BEGIN
   INSERT INTO vendas_backup (...)
   VALUES (...);
END;

## 4. Consultas Analíticas

Consultas desenvolvidas para alimentar o dashboard e gerar indicadores de negócio.

Exemplos:

Faturamento total
Ranking de vendedores
Ticket médio
Quantidade de vendas
Faturamento por cliente
Vendas por marca
Distribuição por tipo de pagamento

# Dashboard Power BI

Após o tratamento dos dados foi desenvolvido um dashboard interativo para análise comercial.

Indicadores implementados:

KPIs Gerais
Faturamento Total
Quantidade de Vendas
Quantidade de Clientes
Ticket Médio
Quantidade de Veículos Disponíveis
Análises Visuais
Faturamento por mês
Faturamento por vendedor
Faturamento por cliente
Faturamento por marca
Distribuição por tipo de pagamento
Percentual de carros vendidos
Filtros Dinâmicos
Mês
Marca
Modelo
Ano de fabricação
Tipo de pagamento

# 👨‍💻 Autor
Desenvolvido por Luis

Sempre evoluindo em:
Data Analytics • SQL • Power BI • Engenharia de Dados
