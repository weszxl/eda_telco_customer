# Análise Exploratória de Dados (EDA) para identificar padrões de cancelamento (churn)

# Contexto
Uma empresa de telecomunicações percebeu que parte de seus clientes está cancelando seus serviços. A diretoria considera utilizar Machine Learning no futuro para identificar clientes com maior risco de cancelamento.

- 1: Entendimento do Negócio (O que é o churn e os objetivos).
- 2: Entendimento dos Dados (Olhar os tipos, nulos ou duplicados).
- 3: Preparação dos Dados (Converter e ajustar). - **Talvez ajustar**
- 4: Criar os gráficos para achar os 3 insights e 3 hipóteses.
- 5: Data Readiness, avaliando se o dado está pronto para o modelo no futuro.
- 6: video





## Data: 

Data columns (total 21 colunas / 7043 linhas):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   customerID        7043 non-null   str          **ID único do cliente**
 1   gender            7043 non-null   str          **Gênero do cliente (Male/Female)**
 2   SeniorCitizen     7043 non-null   int64        **Se o cliente é idoso (1) ou não (0)**
 3   Partner           7043 non-null   str          **Se o cliente tem um parceiro (Yes ou No)**
 4   Dependents        7043 non-null   str          **Se o cliente tem dependentes (Yes ou No)**
 5   tenure            7043 non-null   int64        **Numero de meses de que o cliente contrata a empresa**
 6   PhoneService      7043 non-null   str          **Se o cliente possui serviço de telefone (Yes/No)**
 7   MultipleLines     7043 non-null   str          **Se possui multiplas linhas ou não (Yes/No/No phone service)**
 8   InternetService   7043 non-null   str          **Tipo de serviço de internet (DSL/Fiber optic/No internet service)**
 9   OnlineSecurity    7043 non-null   str          **Serviço extra de segurança online (Yes/No/No internet service)**
 10  OnlineBackup      7043 non-null   str          **Serviço extra de backup online (Yes/No/No internet service)**
 11  DeviceProtection  7043 non-null   str          **Serviço extra de proteção de dispositivo (Yes/No/No internet service)**
 12  TechSupport       7043 non-null   str          **Serviço extra de suporte técnico (Yes/No/No internet service)**
 13  StreamingTV       7043 non-null   str          **Serviço extra de streaming de TV (Yes/No/No internet service)**
 14  StreamingMovies   7043 non-null   str          **Serviço extra de streaming de filmes (Yes/No/No internet service)**
 15  Contract          7043 non-null   str          **Tipo de contrato (Month-to-month/One year/Two year)**
 16  PaperlessBilling  7043 non-null   str          **Se o cliente possui conta sem papel (Yes/No)**
 17  PaymentMethod     7043 non-null   str          **Forma de pagamento (Electronic check/Mailed check/Bank transfer (automatic)/Credit card (automatic))**
 18  MonthlyCharges    7043 non-null   float64      **Valor cobrado mensalmente**
 19  TotalCharges      7043 non-null   str          **O valor total cobrado do cliente até o momento**
 20  Churn             7043 non-null   str          **Se o cliente cancelou o serviço (Yes/No)**    



# Métricas (data.describe())
- Total de Registros (count): 7.043 clientes em todas as colunas (sem valores nulos)
- Idosos (SeniorCitizen): 16,2% da base é composta por idosos (mean = 0.16)
- Tempo de Casa (tenure): Média de 32 meses, com metade dos clientes (50%) até 29 meses e o máximo de 72 meses (6 anos)
- Mensalidade (MonthlyCharges): Média de R$ 64,76, variando entre R$ 18,25 e R$ 118,75
- Gasto Total (TotalCharges): Média acumulada de R$ 2.281,92, chegando ao máximo de R$ 8.684,80

# data.describe(include='all')
- A maior parte  dos clientes é masculino (Male), não tem parceiro (No), não tem dependentes (No), possui serviço de telefone (Yes), não tem múltiplas linhas (No) e usa internet de fibra óptica (Fiber optic)
- Categoria que mais se repetiu: Male (3.555 homens). Serviço de telefone ativo (Yes) (6.361 clientes)

## Coisas boas
-- Sem dados nulos :D / mas tem valores em branco :c
-- Sem dados duplicados :D 
-- Sem duplicidade na capitalização

## Problemas que devem ser resolvidos --- (Tá feito)
- 'TotalCharges' está como string, mas deveria ser float
- 'TotalCharges' tem espaço vazio no lugar do zero, e float não pode ter espaço vazio, tem que ajustar | tem valor em branco, pois clientes novos (tenure) recebem valor 0, em string vira espaço

## churn




















## A considerar (nem precisa)
- remoção da coluna 'customerID' por conta de overfitting, ou transformar em index
- 'SeniorCitizen' está como int64, implicaria na criação de gráficos? (uma função antes de processar deve resolver)
- - - transformar em category do pandas e ajustar para sim ou não?
- 'gender', 'Partner', 'Dependents', 'PhoneService', 'MultipleLines', 'InternetService', 'OnlineSecurity', 'OnlineBackup', 'DeviceProtection', 'TechSupport', 'StreamingTV', 'StreamingMovies', 'Contract', 'PaperlessBilling', 'PaymentMethod', viram caregory (um monte de yes ou no, vira 0 e 1)

## 
