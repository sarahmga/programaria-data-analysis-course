# Análise de Diversidade 2022 – State of Data Brazil
 
O presente repositório contém a versão final do projeto de análise exploratória desenvolvido durante o curso da Programaria, utilizando a base de dados da pesquisa State of Data 2022, do Data Hackers.
 
---
 
## Objetivo
 
Aplicar na prática as etapas de um pipeline de análise de dados: limpeza, transformação, análise estatística e visualização, sobre dados reais do mercado brasileiro da área de dados, com foco em diversidade de gênero, regional e étnico-racial.
 
---
 
## Estrutura do repositório
 
```
├── codes/
│   └── notebook_diversidade_programaria.ipynb   # Notebook com toda a análise
├── dashboard/
│   └── infodash.md                         # Documentação do dashboard no Looker Studio
│   └── Dashboard_Análise_de_Diversidade-1.pdf   # PDF do Dashboard
└── README.md
```
 
---
 
## O que foi praticado
 
- Manipulação e filtragem de dados com **Pandas**
- Tratamento de valores nulos com estratégias segmentadas por faixa
- Detecção e substituição de outliers pelos métodos do desvio padrão e IQR
- Estatística descritiva e intervalo de confiança com **SciPy**
- Correlação entre variáveis contínuas (Pearson) e categóricas (Cramér's V)
- Feature engineering: novas colunas, codificação dummy e merge de tabelas
- Consultas SQL com JOIN e GROUP BY integradas ao pandas via **SQLite**
- Visualização de dados com **Matplotlib**, **Seaborn** e **Plotly**
- Dashboard interativo com três páginas no **Looker Studio**
---
 
## Dashboard
 
O dashboard foi desenvolvido no Looker Studio e está organizado em três páginas:
 
- **Visão Geral**: indicadores principais da pesquisa e distribuição geográfica dos respondentes.
- **Análise de Gênero**: cruzamentos entre gênero, nível de ensino, senioridade, etnia e salário — com filtro por faixa etária.
- **Análise de Etnia**: cruzamentos entre etnia, escolaridade, salário, região e senioridade.
---
 
## Tecnologias
 
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat&logo=python&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat&logo=plotly&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Looker Studio](https://img.shields.io/badge/Looker_Studio-4285F4?style=flat&logo=googleanalytics&logoColor=white)
 
---
 
## Fonte dos dados
 
[State of Data Brazil 2022 – Data Hackers](https://www.datahackers.com.br/)
