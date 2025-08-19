# 📊 Telecom X — Predição de Evasão de Clientes (Churn) — Parte 2

Este repositório corresponde à **Parte 2** do desafio **Telecom X** (Alura).  
Após a limpeza e padronização realizadas na Parte 1, aqui construímos **modelos preditivos** para identificar clientes com **maior risco de evasão (churn)** e os **fatores** que mais influenciam esse comportamento.

> Observação: este repositório é **independente** do repositório da Parte 1, conforme instruções do desafio.

## 📂 Estrutura do Projeto

```
telecom-x-churn/
├── data/              # Dataset tratado (gerado na Parte 1)
├── notebooks/         # Notebooks Jupyter com análise e modelagem
├── images/            # Gráficos e visualizações (opcional)
├── README.md          # Este arquivo
└── requirements.txt   # Dependências do projeto
```

## 🛠️ Tecnologias Utilizadas

- **Python 3.8–3.11**
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Jupyter Notebook

## 🔧 Pipeline

### 1) Preparação dos Dados
- Carregamento do **CSV tratado** da Parte 1 (ex.: `data/dataset_tratado.csv`).
- **Remoção** de colunas irrelevantes (ex.: `customerID`).
- **Encoding** de variáveis categóricas com One-Hot Encoding.
- **Checagem do balanceamento** da variável alvo (`Churn`).
- **Padronização** aplicada para modelos sensíveis à escala (ex.: Regressão Logística).

### 2) Correlação e Seleção de Variáveis
- **Matriz de correlação** entre variáveis numéricas.
- Análises direcionadas (ex.: **Tempo de contrato × Evasão**, **Total gasto × Evasão**).

### 3) Modelagem Preditiva
- **Divisão dos dados**: 70% treino / 30% teste (estratificado).
- Modelos testados:
  - **Regressão Logística** (com padronização).
  - **Random Forest** (sem necessidade de padronização).

### 4) Avaliação dos Modelos
Métricas utilizadas: **Acurácia, Precisão, Recall, F1-score, AUC e Matriz de Confusão**.

| Modelo               | Acurácia | Precisão | Recall | F1-score | AUC  |
|---------------------|----------|----------|--------|----------|------|
| Regressão Logística | 0.801    | 0.635    | 0.533  | 0.579    | 0.843 |
| Random Forest       | 0.779    | 0.593    | 0.444  | 0.508    | 0.810 |

**Conclusão:** a **Regressão Logística** apresentou melhor desempenho, principalmente em Recall e AUC, sendo mais adequada para priorizar clientes em risco.

### 5) Interpretação e Conclusões
- **Importância das variáveis**: Tempo de contrato, Total gasto e tipo de contrato foram fatores relevantes para prever evasão.
- **Insight principal**: Clientes com contratos mensais e baixo tempo de permanência apresentam maior risco de churn.
- **Estratégias sugeridas**: investir em retenção de clientes novos, oferecer benefícios em contratos de longo prazo e acompanhar clientes com baixo gasto.

## ▶️ Como Executar

Você pode executar este projeto de três formas: **venv**, **Conda** ou **Google Colab**.

### Opção 1 – Ambiente Virtual (venv)
```
# Clone o repositório
git clone https://github.com/seu-usuario/telecom-x-churn.git
cd telecom-x-churn

# (Opcional) Crie e ative um ambiente virtual
python -m venv .venv
# Windows
.venv\Scriptsctivate
# macOS/Linux
source .venv/bin/activate

# Instale as dependências
pip install -r requirements.txt

# Execute os notebooks
jupyter notebook
```

### Opção 2 – Usando Conda
```
# Clone o repositório
git clone https://github.com/seu-usuario/telecom-x-churn.git
cd telecom-x-churn

# Crie o ambiente Conda e ative
conda create -n telecomx python=3.10 -y
conda activate telecomx

# Instale as dependências
pip install -r requirements.txt

# Execute os notebooks
jupyter notebook
```

### Opção 3 – Google Colab (sem instalação local)
```
# 1) Clonar o repositório no Colab
!git clone https://github.com/seu-usuario/telecom-x-churn.git
%cd telecom-x-churn

# 2) Instalar dependências
!pip install -r requirements.txt

# 3) Enviar o dataset tratado para a pasta 'data/'
# (na barra lateral do Colab > Arquivos > Upload)
# data/dataset_tratado.csv
```

## 📌 Conclusão Final

Este desafio permitiu aplicar **técnicas de machine learning** para prever a evasão de clientes e identificar os fatores que mais impactam o churn.  
Os resultados reforçam a importância da **retenção de clientes recentes** e da **oferta de contratos de longo prazo**.
