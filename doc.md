# Análise Exploratória de Dados (EDA) para identificar padrões de cancelamento (churn)

## Data: 

Data columns (total 21 columns / 7043 rows):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   customerID        7043 non-null   str    
 1   gender            7043 non-null   str    
 2   SeniorCitizen     7043 non-null   int64  
 3   Partner           7043 non-null   str    
 4   Dependents        7043 non-null   str    
 5   tenure            7043 non-null   int64  
 6   PhoneService      7043 non-null   str    
 7   MultipleLines     7043 non-null   str    
 8   InternetService   7043 non-null   str    
 9   OnlineSecurity    7043 non-null   str    
 10  OnlineBackup      7043 non-null   str    
 11  DeviceProtection  7043 non-null   str    
 12  TechSupport       7043 non-null   str    
 13  StreamingTV       7043 non-null   str    
 14  StreamingMovies   7043 non-null   str    
 15  Contract          7043 non-null   str    
 16  PaperlessBilling  7043 non-null   str    
 17  PaymentMethod     7043 non-null   str    
 18  MonthlyCharges    7043 non-null   float64
 19  TotalCharges      7043 non-null   str       - 11 valores em branco " " (com espaço sendo lido)
 20  Churn             7043 non-null   str    

## Coisas boas
-- Sem dados nulos :D / mas tem valores em branco :c
-- Sem dados duplicados :D
-- 

## Problemas que devem ser resolvidos
- 'TotalCharges' está como string, mas deveria ser float (string não soma, só na merda do python)
- 'TotalCharges' tem espaço vazio no lugar do zero, e float não pode ter espaço vazio, tem que ajustar
- 'Churn' o principal, tem que virar int ou category (ajustado pra 0 e 1) pra calcular a tax de cancelamento

## A considerar
- remoção da coluna 'customerID' por conta de overfitting (llm alucina por causa do formato do ID :D) ou transformar em index
- 'SeniorCitizen' está como int64, implicaria na criação de gráficos? (uma função antes de processar deve resolver)
- - - transformar em category do pandas e ajustar para sim ou não? (não faz sentido calcular idoso - vai tirar média de 0 e 1? mangolão)
- 'gender', 'Partner', 'Dependents', 'PhoneService', 'MultipleLines', 'InternetService', 'OnlineSecurity', 'OnlineBackup', 'DeviceProtection', 'TechSupport', 'StreamingTV', 'StreamingMovies', 'Contract', 'PaperlessBilling', 'PaymentMethod', viram caregory (um monte de yes ou no fica foda pea máquina)
