# Análise de Vendas - Intensivo BI

Este repositório contém o projeto desenvolvido durante o intensivo de Business Intelligence. O objetivo principal foi transformar dados brutos de vendas em insights estratégicos, utilizando ferramentas de ETL e visualização de dados.

## Sobre os Dados
A base de dados utilizada contém informações detalhadas de transações, incluindo:
* **Produtos e Categorias:** Detalhamento do mix de produtos (eletrônicos, eletrodomésticos, etc).
* **Financeiro:** Preço unitário, custos e margens de lucro.
* **Geografia:** Vendas abrangendo América do Sul, Europa, Ásia e América do Norte.
* **Clientes e Marcas:** Identificação de perfis de compra e performance de marcas como Litware e Northwind Traders.

## Tecnologias e Ferramentas
* **Power BI:** Criação do dashboard interativo e dashboards de performance.
* **Power Query (Linguagem M):** Limpeza de dados, tratamento de valores nulos, tipagem e modelagem dimensional.
* **DAX:** Desenvolvimento de medidas para análise de vendas e indicadores de negócio.

##  Processo de ETL e Tratamento de Dados
O processo de extração e transformação foi realizado no Power Query, garantindo a qualidade da base antes da modelagem:

1. **Limpeza de Nulos:** Identificação e remoção de registros nulos para evitar distorções em cálculos de médias e somatórios.
2. **Tratamento de Strings (Nomes):** * Utilizei a técnica de inversão de colunas com base em delimitadores para transformar o formato "Sobrenome, Nome" em "Nome Sobrenome", melhorando a legibilidade e a classificação alfabética nos visuais.
3. **Divisão de Colunas (Geografia):** * A coluna original de Localidade foi dividida utilizando o delimitador " - ", resultando em duas colunas distintas: **País** e **Continente**. Isso possibilita a criação de hierarquias geográficas no Power BI.
4. **Cálculos Aritméticos:** * Realizei a multiplicação entre as colunas de `Quantidade Vendida` e `Preço Unitário` diretamente no Power Query para gerar a coluna de **Faturamento Bruto**, otimizando o modelo de dados.
5. **Tipagem de Dados:** * Conversão e conferência de tipos (Moeda para valores financeiros, Data para cronologia e Inteiros para quantidades) para assegurar a performance das medidas DAX.

## Visualização do Projeto
Aqui está uma prévia do dashboard finalizado:

![Dashboard de Vendas](./img/dash_sales.png)

## Autor
Rodrigo Pinesso.