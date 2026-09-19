## Estrutura do projeto

```text
/telco_eda_customer
│
├── /docs
│   ├── entendimento_negocio.md  # Contexto, problema, stakeholders e objetivos
│   └── notes.md                 # anotações/rascunhos durante a visualização dos dados
│
├── /data                        # dataset base e limpo
│
├── requirements.txt             # bibliotecas necessárias
└── analise.ipynb                # código da EDA
```

## Configuração do ambiente local

### 1. Pré-requisitos

- As extensões de **Python** e **Jupyter**

### 2. Ambiente virtual

na raiz `/telco_eda_customer`, rode:

```bash
python -m venv venv
```

### 3. Ativar o ambiente

- **No Windows:**
  ```cmd
  venv\Scripts\activate
  ```
- **No Linux ou mac:**
  ```bash
  source venv/bin/activate
  ```

### 4. Instalando as bibliotecas

```bash
pip install -r requirements.txt
```