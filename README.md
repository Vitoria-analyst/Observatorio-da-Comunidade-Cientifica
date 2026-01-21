# 🔬 Observatório da Comunidade Científica (UA)

> **Uma abordagem de Inteligência Bibliométrica com Modelagem de Tópicos (NMF) e GenAI (Llama 3).**

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://observatoriocientifico.streamlit.app/) 
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Sobre o Projeto

Este projeto foi desenvolvido no âmbito do Mestrado em Ciência de Dados para Ciências Sociais da Universidade de Aveiro. O objetivo foi criar uma ferramenta capaz de analisar a estrutura, evolução e distribuição da produção científica da universidade, indo além das métricas tradicionais de contagem.

Utilizando dados da **Scopus (2020-2025)**, o sistema aplica técnicas de **Processamento de Linguagem Natural (NLP)** para extrair tendências temáticas latentes nos resumos dos artigos e apresenta os resultados num dashboard interativo desenvolvido em Streamlit.

### 🚀 Funcionalidades Principais

* **📊 Painel de Desempenho:** Métricas de produtividade, citações e índice-h por departamento e autor.
* **🤖 Modelagem de Tópicos (Topic Modeling):** Uso do algoritmo **NMF (Non-negative Matrix Factorization)** para categorizar automaticamente milhares de *abstracts* em temas coerentes.
* **🧠 Enriquecimento Semântico com LLM:** Integração inovadora com **Llama 3** para gerar rótulos legíveis e descrições humanas para os tópicos matemáticos identificados.
* **📈 Tendências Temporais:** Classificação automática de tópicos em "Consolidados" vs. "Emergentes".
* **🌍 Redes de Colaboração:** Análise geoespacial das parcerias internacionais da instituição.

---

## 🛠️ Tecnologias e Ferramentas

O projeto utiliza uma stack focada em Data Science e Web Dev em Python:

* **Linguagem:** Python 3
* **Dashboard:** [Streamlit](https://streamlit.io/)
* **Visualização:** Plotly Express & Plotly Graph Objects
* **NLP & ML:**
    * `scikit-learn` (NMF, TF-IDF)
    * `spaCy` (Pré-processamento, NER, Lemmatization)
* **GenAI:** Llama 3 (via `ollama`) para rotulagem de tópicos.
* **Dados:** Pandas, NumPy.

---

## 📂 Estrutura do Repositório

```bash
├── app.py                                # Aplicação principal (Dashboard Streamlit)
├── AnaliseBibliometrica_E_Conteudo.ipynb # Notebook: Ingestão, Limpeza, EDA e Modelo NMF
├── Enriquecimento_ParaODashboard.ipynb   # Notebook: Integração com Llama 3 para rotulagem
├── data/                                 # Pasta com os CSVs processados
├── requirements.txt                      # Dependências do projeto
└── README.md                             # Documentação
```

---

⚙️ Metodologia e Pipeline
O fluxo de dados segue três etapas principais detalhadas nos notebooks:

1. Ingestão e Processamento
Coleta: Extração de metadados bibliográficos da Scopus.

NLP: Pipeline com spaCy para tokenização, remoção de stopwords e filtragem gramatical (apenas substantivos e adjetivos para reduzir ruído).

Vetorização: TF-IDF com n-grams para representação numérica dos textos.

2. Modelagem e GenAI
NMF (Non-negative Matrix Factorization): Fatorização da matriz TF-IDF em 10 tópicos latentes. Este algoritmo foi escolhido pela sua interpretabilidade superior em textos curtos (abstracts) comparado ao LDA.

LLM Labeling: Os vetores de palavras de cada tópico foram enviados ao Llama 3, que retornou um nome curto e uma descrição para cada tema (ex: transformando uma lista de palavras como "solar, cells, energy" em "Energias Renováveis").

3. Visualização
Construção da interface em Streamlit (app.py).

Implementação de filtros dinâmicos que cruzam dados temporais com tópicos semânticos.

🖥️ Como Executar Localmente
Siga estes passos para rodar o dashboard na sua máquina:

Clone o repositório:

Bash

git clone [https://github.com/SEU_USUARIO/NOME_DO_REPO.git](https://github.com/Vitoria-analyst/Observatorio-da-Comunidade-Cientifica.git)
cd Observatorio-da-Comunidade-Cientifica
Instale as dependências:

Bash

pip install -r requirements.txt
Execute o Streamlit:

Bash

streamlit run app.py

---
👩‍💻 Autores
Vitória Rodrigues - [LinkedIn](https://www.linkedin.com/in/vitoria-rodrigues-/)
