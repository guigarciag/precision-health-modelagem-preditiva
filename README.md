# Projeto de Previsão de No-show em Consultas Médicas

## Visão Geral
Este projeto tem como objetivo desenvolver um modelo de Machine Learning para prever se um paciente irá ou não comparecer a uma consulta médica (`no-show`). A análise explora diversos fatores que podem influenciar o `no-show` e utiliza modelagem dimensional para estruturar os dados.

## Estrutura do Projeto
```
project_root/
├── notebooks/
│   └── <seu_notebook>.ipynb  (Este arquivo)
├── models/
│   └── modelo_final.joblib   (Modelo treinado exportado)
├── requirements.txt         (Dependências do projeto)
└── README.md                (Este arquivo)
```

## Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone <URL_DO_SEU_REPOSITORIO>
    cd <nome_do_repositorio>
    ```

2.  **Crie e ative um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: .env\Scriptsctivate
    ```

3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Execute o Notebook:**
    Abra o arquivo `.ipynb` na pasta `notebooks/` em um ambiente como Jupyter Notebook ou Google Colab e execute todas as células para reproduzir a análise e o treinamento do modelo.

## Modelagem Dimensional
Os dados foram estruturados em um Star Schema, composto por:
*   **Tabela de Fatos:** `Fact_Appointments`
*   **Tabelas de Dimensão:** `Dim_Patient`, `Dim_Date`, `Dim_Time`, `Dim_Doctor`, `Dim_Clinic`

## Análise Exploratória de Dados (EDA)
Foram realizadas análises para entender a distribuição das variáveis e a relação com a taxa de `no-show`. Principais insights:
*   `previous_no_shows`: Forte preditor de `no-show`.
*   `reminder_sent`: Lembretes reduziram a taxa de `no-show`.
*   `patient_age` e `waiting_time_minutes`: Influência notável na taxa de `no-show`.

## Modelagem Preditiva
Foram treinados e avaliados os seguintes modelos de classificação para prever o `no_show_flag`:
*   Regressão Logística
*   Random Forest Classifier
*   Gradient Boosting Classifier

O modelo de **Gradient Boosting Classifier** foi selecionado como o modelo final devido ao seu desempenho ligeiramente superior nas métricas de avaliação, especialmente o AUC-ROC, para o desafio de prever `no-show` com dados desbalanceados.

## Integrantes
*   Guilherme Gonçalves Garcia
*   Lohan Batista Moreira
*   Paulo Henrique dos Santos Tristão
*   Rodrigo Puertas Matioli
