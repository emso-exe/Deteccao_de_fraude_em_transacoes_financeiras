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

### Dicionário de dados

Com base no entendimento dos dados foi elaborado este dicionário.

1. **Dados de Transações (transactions_data.csv)**

| Nome da Coluna    | Tipo     | Descrição |
|-------------------|---------|-----------|
| `id`             | Int     | Identificador único da transação. |
| `date`           | String  | Data e hora da transação (AAAA-MM-DD HH:MM:SS). |
| `client_id`      | Int     | Identificador do cliente que realizou a transação. |
| `card_id`        | Int     | Identificador do cartão utilizado na transação. |
| `amount`         | String  | Valor da transação (em formato monetário). |
| `use_chip`       | String  | Tipo de transação (Swipe Transaction, Online Transaction e Chip Transaction). |
| `merchant_id`    | Int     | Identificador do comerciante. |
| `merchant_city`  | String  | Cidade do comerciante. |
| `merchant_state` | String  | Estado do comerciante (pode ser `NULL` para transações online). |
| `zip`            | Float   | Código postal do comerciante (pode ser `NULL` para transações online). |
| `mcc`            | Int     | Código da categoria do comerciante (Merchant Category Code). |
| `errors`         | String  | Erros na transação (`NULL` se não houver erro). |

2. **Informações de Cartões (cards_data.csv)**
| Nome da Coluna          | Tipo       | Descrição |
|-------------------------|-----------|-----------|
| `id`                   | Int       | Identificador único do cartão. |
| `client_id`            | Int       | Identificador do cliente associado ao cartão. |
| `card_brand`           | String    | Bandeira do cartão (Visa, Mastercard, Discover e Amex). |
| `card_type`            | String    | Tipo de cartão (Credit, Debit e Debit (Prepaid)). |
| `card_number`          | String    | Número do cartão (possivelmente mascarado). |
| `expires`              | String    | Data de expiração do cartão (MM/AAAA). |
| `cvv`                  | Int       | Código de verificação do cartão. |
| `has_chip`             | String    | Indica se o cartão possui chip (YES/NO). |
| `num_cards_issued`     | Int       | Número total de cartões emitidos para o cliente. |
| `credit_limit`         | String    | Limite de crédito do cartão (em formato monetário). |
| `acct_open_date`       | String    | Data de abertura da conta do cartão (MM/AAAA). |
| `year_pin_last_changed`| Int       | Ano da última alteração do PIN. |
| `card_on_dark_web`     | String    | Indica se o cartão foi encontrado na dark web (Yes/No). |

3. **Códigos de Categoria de Comerciantes (mcc_codes.json)**
| Nome da Coluna  | Tipo    | Descrição |
|-----------------|--------|-----------|
| `code`         | Int    | Código de categoria do comerciante (MCC - Merchant Category Code). |
| `description`  | String | Descrição da categoria do comerciante. |

4. **Rótulos de Fraude (train_fraud_labels.json)**
| Nome da Coluna     | Tipo    | Descrição |
|--------------------|--------|-----------|
| `transaction_id`  | Int    | Identificador único da transação. |
| `is_fraud`        | String | Indica se a transação foi fraudulenta (Yes/No). |

5. **Dados de Usuários (users_data.csv)**
| Nome da Coluna         | Tipo       | Descrição |
|------------------------|-----------|-----------|
| `id`                  | Int       | Identificador único do cliente. |
| `current_age`         | Int       | Idade atual do cliente. |
| `retirement_age`      | Int       | Idade esperada para aposentadoria. |
| `birth_year`          | Int       | Ano de nascimento do cliente. |
| `birth_month`         | Int       | Mês de nascimento do cliente. |
| `gender`              | String    | Gênero do cliente (Male/Female). |
| `address`             | String    | Endereço residencial do cliente. |
| `latitude`            | Float     | Latitude do endereço do cliente. |
| `longitude`           | Float     | Longitude do endereço do cliente. |
| `per_capita_income`   | String    | Renda per capita do cliente (em formato monetário). |
| `yearly_income`       | String    | Renda anual do cliente (em formato monetário). |
| `total_debt`          | String    | Dívida total do cliente (em formato monetário). |
| `credit_score`        | Int       | Pontuação de crédito do cliente. |
| `num_credit_cards`    | Int       | Número de cartões de crédito ativos do cliente. |

> fonte: [Financial Transactions Dataset: Analytics](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets)

## 💻 Tecnologias

## 💳 Créditos

- [Estênio Mariano](https://github.com/emso-exe)

## 🔖 Licença

Licença MIT (MIT). Por favor leia o [arquivo da licença](LICENSE.md) para mais informações.