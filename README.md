# Pipeline de Dados E-commerce (Olist) - Arquitetura Medalhão no Databricks

Este projeto implementa um pipeline de dados completo (ETL) utilizando o dataset da Olist. O grande diferencial deste projeto é a ingestão dinâmica de dados via **API REST**, simulando um ambiente corporativo real de extração, seguida pela aplicação da **Arquitetura Medalhão** (Bronze, Silver e Gold) para transformar os dados brutos em insights de negócio escaláveis.

## 🚀 Tecnologias Utilizadas
* **Databricks** (Ambiente de processamento distribuído)
* **Python & Requests** (Conexão com API e extração de dados JSON/dinâmicos)
* **PySpark & Spark SQL** (Motor de processamento de dados)
* **Delta Lake** (Armazenamento de alta performance com transações ACID)

## 🏗️ Arquitetura do Projeto
O pipeline foi dividido em três notebooks modulares para garantir organização e escalabilidade:

1.  **01_ingestao_bronze**: Responsável pela conexão com a API da Olist, extração dos dados via requisições HTTP e armazenamento seguro no ambiente Databricks, criando as visualizações iniciais (fiel à origem).
2.  **02_transformacao_silver**: Etapa de limpeza e refino. Aqui os dados brutos são tipados (datas, números decimais), strings são padronizadas e os dados são persistidos no formato otimizado **Delta Table**.
3.  **03_analytics_gold**: Camada de negócio onde ocorrem as agregações e os JOINS. O foco é gerar tabelas prontas para consumo de BI, como o faturamento consolidado por estado (UF).

## 📊 Principais Insights
Através da camada Gold, foi possível estruturar consultas SQL otimizadas para identificar o faturamento real (pedidos entregues), separando o valor do produto e o frete, permitindo uma visão clara da performance por região brasileira.

## 🛠️ Como Executar
1. Clone este repositório no seu Databricks via **Git Folders**.
2. Configure as credenciais ou parâmetros da API no notebook `01_ingestao_bronze`.
3. Execute os notebooks na ordem numérica (01 -> 02 -> 03).

---
*Projeto desenvolvido por [Willian Matos](https://github.com/willian_smatos)*
