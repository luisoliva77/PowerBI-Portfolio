# ✈️ Dashboard de Viagens a Serviço

Dashboard analítico em Power BI para acompanhamento de viagens a serviço de servidores públicos federais (diárias e passagens), cobrindo o período de 2023 a 2024.


# 📋 Sobre os dados

A base (viagens_limpo) contém 833.160 registros, com informações de processo, viajante, período, destino e valores de cada viagem — incluindo identificação do órgão, cargo/função do viajante, situação (realizada/não realizada), indicação de urgência e detalhamento financeiro (diárias, passagens, devolução e outros gastos).

MétricaValorTotal de registros833.160Viajantes únicos232.247Órgãos superiores35Período cobertojan/2023 – dez/2024


# 🗂️ Modelo de dados

Tabelas:


viagens_limpo — tabela fato, com os dados brutos de cada viagem.
Calendario — tabela calculada, marcada como Date Table, cobrindo todo o intervalo de datas de início e fim das viagens. Contém colunas de Ano, Trimestre, Semestre, Mês (nome e abreviação, ordenados corretamente), Dia, Dia da Semana e indicador de Fim de Semana.


Relacionamentos:


Calendario[Data] → viagens_limpo[Período - Data de início] — ativo
Calendario[Data] → viagens_limpo[Período - Data de fim] — inativo (ativado via USERELATIONSHIP quando necessário)


Hierarquia: Hierarquia de Datas — Ano → Trimestre → Mês → Dia, para drill-down nos visuais.


# 📐 Medidas DAX

27 medidas organizadas em 5 pastas de exibição:

PastaMedidas01. VolumetriaTotal de Viagens, Total de Propostas (PCDP), Total de Viajantes, Total de Órgãos, Viajantes por Proposta02. FinanceiroTotal Diárias, Total Passagens, Total Devolução, Total Outros Gastos, Gasto Bruto Total, Gasto Líquido Total, Gasto Médio por Viagem, Gasto Médio por Viajante, % Devolução sobre Gasto Bruto03. Status e UrgênciaTotal/% Viagens Realizadas, Total/% Viagens Urgentes, Total/% Viagens Sem Custo04. DuraçãoTotal de Dias de Viagem, Duração Média/Máxima da Viagem, Gasto Médio por Dia de Viagem05. Comparativos TemporaisGasto Líquido Ano Anterior, Variação YoY (R$ e %), Gasto Líquido YTD, Total de Viagens (Data de Fim)


# 📊 Página "Visão Geral"

Cabeçalho: título, período do relatório e painel de filtragem (intervalo de datas, Órgãos Superiores, Situação e Viagem Urgente, com botão "Limpar Filtros").

Cards de KPI: Gasto Médio por Viagem · Total de Viajantes · Gasto Líquido Total · % Viagens Urgentes · % Viagens Sem Custo.

Linha de gráficos (meio):


Gasto Líquido Total por MesAbrev — área/linha com a tendência mensal do gasto.
Total de Viagens e % Viagens Urgentes por Mês — combo colunas + linha, cruzando volume com taxa de urgência.
Total Diárias, Total Outros Gastos e Total Passagens — rosca com a composição do gasto (Passagens 62,7% · Diárias 36,8% · Outros 0,6%).


Linha de detalhamento (base):


Tabela de Total de Viagens por Órgão Superior.
Gasto Médio por Órgão — barras horizontais.
Total de Viagens Realizadas por Cargo — barras horizontais.



# 🔍 Principais insights identificados


O Ministério da Justiça e Segurança Pública lidera em volume (201.940 viagens) e gasto (R$ 782 mi), mas tem a menor proporção de viagens urgentes (41,3%) — perfil de viagens mais planejadas frente aos demais órgãos.
Janeiro concentra o menor volume de viagens do ano, mas a maior % de urgência (~70%) — indício de que o ciclo de planejamento orçamentário ainda não está "rodando" no início do exercício.
Novembro é o pico de volume de viagens, sem aumento proporcional de urgência — sinal de que o maior movimento do ano é bem planejado.
Passagens representam quase 2/3 do gasto total, bem à frente de diárias (37%) e outros gastos (praticamente irrelevantes, 0,6%).

# Origem dos dados

Toda base de dados foi devidamente tratada a partir de uma pipeline de dados no Python
para analisar todo o processo de tratamento, acessar o link do projeto: 
https://github.com/luisoliva77/Portfolio-Pandas/tree/main/Projeto_Pipeline
