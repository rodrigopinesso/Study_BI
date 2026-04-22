# 📊 Dashboard RH — People Analytics

Painel de RH desenvolvido no **Power BI** para análise de pessoas, acompanhamento de contratações, turnover e distribuição da força de trabalho por área, cargo, cidade e gênero.

---

## 🖼️ Visão Geral

![Dashboard RH](img/dash_rh.png)

---

## 🎯 Objetivo

Fornecer uma visão analítica do capital humano da empresa, permitindo que gestores de RH acompanhem indicadores estratégicos como contratações ao longo do tempo, taxa de turnover, distribuição de funcionários ativos por área e cargo, e composição por gênero e localização.

---

## 📌 Indicadores do Painel

| Indicador | Descrição |
|---|---|
| **Contratações** | Evolução do número de contratações ao longo do tempo |
| **Func. Ativos** | Total de funcionários ativos no período |
| **Desligados** | Quantidade de funcionários desligados |
| **Turnover** | Taxa de rotatividade da empresa |
| **Func. Ativos por Cidade** | Ranking de cidades com maior número de colaboradores |
| **Func. Ativos por Gênero** | Distribuição percentual entre masculino e feminino |
| **Func. Ativos por Área e Cargo** | Fluxo de funcionários segmentado por área (Administrativo, Comercial, Operações, Logística, Financeiro) e nível de cargo (Estagiário, Analista, Coordenador, Gerente) |

---

## 🗂️ Estrutura do Projeto

```
hr_BI/
│
├── dash/
│   └── hr_dash.pbix          # Arquivo do painel Power BI
│
├── data/
│   └── BaseFuncionarios.xlsx  # Base de dados com informações dos colaboradores
│
└── img/
    └── dash_rh.png            # Preview do dashboard
```

---

## 🗃️ Sobre os Dados

A base `BaseFuncionarios.xlsx` contém informações de colaboradores com os seguintes campos:

- **ID RH** — Identificador único do funcionário
- **Nome** — Nome do colaborador
- **Gênero** — M / F
- **Cidade** — Localização do colaborador
- **Data de Contratação** — Data de início na empresa
- **Data de Demissão** — Data de saída (quando aplicável)
- **Salário** — Remuneração do colaborador
- **Cargo** — Estagiário, Analista, Coordenador ou Gerente
- **Área** — Administrativo, Comercial, Operações, Logística ou Financeiro
- **Horas Extras** — Total de horas extras registradas
- **Avaliação do Funcionário** — Nota de desempenho

---

## 🛠️ Tecnologias Utilizadas

- [Power BI Desktop](https://powerbi.microsoft.com/) — Modelagem de dados e visualizações
- Microsoft Excel — Fonte de dados (`BaseFuncionarios.xlsx`)
- DAX — Criação de medidas e KPIs

---

## 🚀 Como Utilizar

1. Clone ou baixe este repositório
2. Abra o arquivo `dash/hr_dash.pbix` no **Power BI Desktop**
3. Verifique se o caminho da fonte de dados aponta corretamente para `data/BaseFuncionarios.xlsx`
4. Atualize os dados e explore o painel

---

## 👤 Autor

**Rodrigo Pinesso**  
[GitHub](https://github.com/rodrigopinesso/Study_BI)