# Finance BI Dashboard

Dashboard financeiro desenvolvido em Power BI para análise de movimentações bancárias, com foco em receita, despesas, impostos e lucratividade por banco, município e período.

## Preview

![Finance Dashboard](img/finance_dash.png)

![Dashboard filtrado por Santander](img/dash_santander.png)

## Sobre o projeto

O objetivo deste dashboard é oferecer uma visão consolidada das movimentações financeiras de múltiplos bancos, permitindo análises comparativas por instituição, forma de pagamento, município e evolução temporal do lucro. A construção priorizou clareza na leitura dos dados e fluidez na narrativa analítica.

## Técnicas utilizadas

### Ticker Scroller (Rolagem de KPIs no topo)

Na borda superior do dashboard foi implementado um **ticker scroller** — uma faixa de rolagem automática que exibe os KPIs de participação de mercado por município em tempo real, similar ao modelo utilizado em painéis financeiros e bolsas de valores.

A técnica consiste em criar uma medida DAX que concatena dinamicamente os valores de cada cidade com seus respectivos percentuais e variações, exibida em um visual de cartão com animação de rolagem configurada via HTML/CSS dentro de um visual personalizado ou iframe embeddado no relatório. Isso permite que o usuário leia rapidamente os indicadores de todas as praças — São Paulo, Rio de Janeiro, Vitória e Belo Horizonte — sem ocupar espaço permanente no layout.

**Benefício:** condensar múltiplas métricas geográficas em uma única linha visual, liberando o corpo do dashboard para análises mais detalhadas.

### Data Storytelling

O dashboard foi estruturado com princípios de **data storytelling** para guiar o olhar do analista de forma intuitiva:

**Hierarquia visual:** os KPIs principais (Receita, Despesas, Imposto e Lucro) aparecem no topo em cards de destaque, estabelecendo o contexto macro antes de qualquer detalhe.

**Narrativa em texto dinâmico:** o painel lateral direito traz uma sentença gerada por DAX que traduz os números em linguagem natural — informando o total de transações, o volume via PIX e o percentual que ele representa. Esse bloco de texto atua como narrador do dashboard, ancorando o leitor na história dos dados antes de explorar os visuais.

**Seleção por banco como filtro narrativo:** o painel de logos bancários no canto esquerdo funciona como um seletor visual que recontextualiza toda a narrativa. Ao clicar em Santander, por exemplo, o texto, os KPIs e o gráfico de cascata se atualizam para contar a história específica daquela instituição — margem de lucro de 48,61%, 414 transações, participação relevante do PIX.

**Gráfico de cascata mensal:** o visual de Lucro por Mês no rodapé utiliza o formato waterfall (cascata), ideal para storytelling financeiro pois evidencia meses de perda (barras vermelhas) e ganho (cinza), culminando no total acumulado em verde. Isso cria uma narrativa temporal clara: onde o resultado piorou, onde se recuperou e qual foi o saldo final.

## Estrutura do repositório

```
finance_BI/
├── dash/
│   └── finance_dash.pbix       # Arquivo do dashboard Power BI
├── data/
│   └── Base Financeiro.xlsx    # Base de dados com 2.725 movimentações
└── img/
    ├── finance_dash.png         # Preview geral do dashboard
    └── dash_santander.png       # Preview com filtro Santander ativo
```

## Base de dados

A planilha `Base Financeiro.xlsx` contém 2.725 registros de movimentações financeiras com os seguintes campos:

| Campo | Descrição |
|---|---|
| Numero Movimentacao | Identificador da transação |
| Nome | Empresa envolvida |
| Município | Praça da operação |
| Data da Movimentacao | Data da transação |
| Valor da Movimentação | Valor em reais |
| Tipo | Recebimento ou Pagamento |
| Banco | Instituição financeira |
| Imagem | URL do logo do banco |
| Forma Pagamento | PIX, Boleto, Cartão ou MercadoPago |

**Bancos cobertos:** Itaú, Nubank, Bradesco, Santander, Safra

**Municípios:** São Paulo, Rio de Janeiro, Belo Horizonte, Vitória

**Período:** Janeiro a Dezembro de 2020

## Métricas calculadas via DAX

- **Receita** — soma dos valores do tipo Recebimento
- **Despesas** — soma dos valores do tipo Pagamento
- **Imposto** — calculado sobre a receita
- **Lucro** — Receita menos Despesas e Impostos
- **Margem de Lucro** — Lucro dividido pela Receita
- **Participação PIX** — percentual de transações realizadas via PIX
- **Texto narrativo dinâmico** — medida que gera a sentença descritiva exibida no painel lateral

## Ferramentas

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Microsoft Excel