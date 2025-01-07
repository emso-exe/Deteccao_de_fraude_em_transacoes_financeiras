# 🔎 Detecção de fraude em transações financeiras 💳

Este projeto visa a análise de dados e a construção de um modelo de machine learning para detecção de fraudes em transações financeiras. Os dados utilizados foram extraídos do Kaggle e estão disponíveis em: [Financial Transactions Dataset: Analytics](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets). Este abrangente conjunto de dados financeiros combina registros de transações, informações de clientes e dados de cartões de uma instituição bancária, abrangendo toda a década de 2010.

## 🚨 Contexto do problema

Com o avanço das tecnologias de transações bancárias, cada vez mais rápidas e acessíveis de múltiplos dispositivos, detectar transações fraudulentas tornou-se essencial para a excelência nos negócios das instituições financeiras.
A precisão na identificação de transações ilegítimas é imperativa para prevenir perdas financeiras, proteger os clientes e garantir a confiança no sistema financeiro. Este cenário exige soluções automatizadas e eficientes baseadas em dados.

## 💼 Demanda do negócio

O objetivo é desenvolver um modelo preditivo de alta precisão, capaz de identificar, com confiabilidade, se uma transação é fraudulenta ou legítima, contribuindo para o fortalecimento das políticas de segurança financeira da instituição.

## 📃 Compreensão dos dados

Os dados utilizados neste projeto estão disponíveis no Kaggle ([Financial Transactions Dataset: Analytics](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets)) e incluem **arquivos CSV** e **arquivos JSON** contendo registros detalhados de transações financeiras, informações relacionadas aos clientes, dados complementares sobre os cartões utilizados e outros aspectos relevantes.
Esses dados oferecem um panorama rico para a análise exploratória e a modelagem preditiva.

### Componentes do Conjunto de Dados

1. **Dados de Transações (transactions_data.csv)**
   - Registros detalhados de transações, incluindo valores, datas e detalhes dos comerciantes.
   - Abrange transações ao longo da década de 2010.
   - Contém tipos de transações, valores e informações sobre os comerciantes.

2. **Informações de Cartões (cards_data.csv)**
   - Detalhes de cartões de crédito e débito.
   - Inclui limites dos cartões, tipos e datas de ativação.

3. **Códigos de Categoria de Comerciantes (mcc_codes.json)**
   - Códigos padrão de classificação para tipos de negócios.
   - Códigos MCC (Merchant Category Codes) com descrições baseadas em padrões da indústria.

4. **Rótulos de Fraude (train_fraud_labels.json)**
   - Rótulos binários para classificação de transações.
   - Indica se uma transação é fraudulenta ou legítima.

5. **Dados de Usuários (users_data.csv)**
   - Informações demográficas sobre os clientes.
   - Detalhes relacionados às contas.

> fonte: [Financial Transactions Dataset: Analytics](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets)

## 💻 Tecnologias

## 💳 Créditos

- [Estênio Mariano](https://github.com/emso-exe)

## 🔖 Licença

Licença MIT (MIT). Por favor leia o [arquivo da licença](LICENSE.md) para mais informações.