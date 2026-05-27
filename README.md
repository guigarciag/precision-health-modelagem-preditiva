# PREDICTIVE HEALTHCARE APPOINTMENT NO-SHOWS

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Status](https://img.shields.io/badge/STATUS-CONCLUÍDO-green?style=for-the-badge)

## 📌 Descrição do Projeto
Este projeto foi desenvolvido como parte da disciplina de **Projeto Final de Engenharia de Computação**. A solução aborda o problema do impacto financeiro e operacional causado por faltas de pacientes a consultas agendadas, utilizando um pipeline completo de Engenharia de Dados, Análise Estatística, Machine Learning e Business Intelligence para prever a probabilidade de absenteísmo (*no-show*).

---

## 👥 Equipe
* **Guilherme Gonçalves Garcia** - RA: 082210014
* **Lohan Batista Moreira** - RA: 082210035
* **Paulo Henrique dos Santos Tristão** - RA: 082210017
* **Rodrigo Puertas Matioli** - RA: 082210037

---

## 🚀 Entregas e Metodologia

### M1: Data Engineering (Pipeline ETL)
Estruturação de um pipeline robusto para consumo do dataset de análise de tempo de espera e no-show na saúde via `kagglehub`.
* **Arquitetura:** Implementação de **Star Schema** envolvendo a tabela de fatos `Fact_Appointments` e as dimensões `Dim_Patient`, `Dim_Date`, `Dim_Time`, `Dim_Doctor` e `Dim_Clinic`.
* **Armazenamento:** Estrutura com injeção de metadados temporais de controle ETL (`etl_load_tms`, `etl_updt_tms`, `etl_row_id`) executada no ambiente do Google Colab.
* **Tecnologias:** Python, Pandas, Google Colab.

### M2: Exploratory Data Analysis (EDA)
Exploração estatística para validação de hipóteses e inteligência de dados.
* **Análise Univariada/Multivariada:** Identificação de forte assimetria positiva na variável de tempo de espera, com mediana de 88.0 minutos e média de 90.19 minutos. A taxa global de no-show identificada na base de dados é de aproximadamente 23.07%.
* **Correlação:** Avaliação de fatores de impacto categóricos e numéricos em relação à variável alvo `no_show_flag`.
* **Insight Chave:** O histórico do paciente é o indicador mais forte: a taxa de no-show cresce de maneira linear e consistente à medida que o número de faltas anteriores (`previous_no_shows`) aumenta. Adicionalmente, o envio de lembretes reduz drasticamente o absenteísmo (21.6% de no-show para quem recebeu vs 28.5% para quem não recebeu).

### M3: Modelagem Preditiva (Machine Learning)
Desenvolvimento de modelos para Classificação da variável `no_show_flag`.

| Modelo | Acurácia/R² | F1-Score / RMSE | Status |
| :--- | :--- | :--- | :--- |
| Regressão Logística | 0.77 | 0.00 | Testado |
| Random Forest | 0.76 | 0.03 | Testado |
| Gradient Boosting (Original) | 0.77 | 0.02 | Testado |
| Gradient Boosting (Otimizado) | 0.77 | 0.05 | **Final** |

* **Vencedor:** O algoritmo **Gradient Boosting Classifier** foi escolhido como modelo final. Contudo, a análise de estresse e o veredicto estratégico apontaram um *ponto cego logístico*: os modelos de comportamento histórico atuam como um espelho retrovisor e são insuficientes por si só para sustentar decisões automatizadas de *overbooking* sem a inclusão de determinantes externos em tempo real (como tráfego urbano e microlocalização).

### M4: Business Insights & GenAI

---

## 📺 Apresentação e Demonstração

Para uma visão completa da solução, acesse os links abaixo:

> 🎥 **[ASSISTIR AO VÍDEO DO PITCH (2 MIN)](LINK_DO_VIDEO_AQUI)**
> *Resumo do tema, problema, metodologia e solução final.*

> 🤖 **[ACESSAR AGENTE DE INSIGHTS - GOOGLE AI STUDIO](https://ai.studio/apps/a7020c43-a39a-492b-a656-92949a4cd4fa)**
> *Interaja com a nossa IA treinada para analisar os dados deste projeto.*

---

## 🛠️ Como Reproduzir
1. Clone o repositório: `git clone [URL_DO_REPO]`
2. Instale as dependências: `pip install -r requirements.txt`
3. Abra os notebooks na pasta `/notebooks` via Google Colab.
4. Certifique-se de configurar o caminho do Google Drive para a leitura dos arquivos em `/data`.

---

<p align="center">
  <img src="https://faculdadesalvadorarena.org.br/wp-content/uploads/2022/07/logo_fesa.png" width="200" alt="Logo Faculdade Engenheiro Salvador Arena"><br>
  <b>Faculdade Engenheiro Salvador Arena</b><br>
  Curso de Engenharia de Computação | Março de 2026
</p>
