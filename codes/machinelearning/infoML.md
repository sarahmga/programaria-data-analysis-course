# Regressão Linear – Previsão de Salários
 
Notebook desenvolvido como parte do projeto da Programaria, aplicando um modelo de regressão linear para prever o salário de profissionais de dados com vínculo CLT, com base na pesquisa State of Data 2022. A etapa de preparação dos dados envolveu filtragem por vínculo empregatício, remoção de categorias com poucos registros, extração de valores numéricos a partir de campos textuais com expressões regulares, criação de variáveis binárias e codificação ordinal do nível de ensino.
 
O modelo foi treinado com `scikit-learn` após divisão treino/teste (80/20) e normalização com `StandardScaler`. A avaliação utilizou três métricas — MSE, MAE e R² — e os resultados (R² de 0,52 e MAE de ~R$ 3.291) indicam um modelo com capacidade preditiva moderada, insuficiente para uso em produção mas adequado para fins de análise. O notebook encerra com uma reflexão sobre os riscos de reprodução de vieses sociais em modelos treinados sobre dados que refletem desigualdades reais de mercado.
 
## Tecnologias
 
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=python&logoColor=white)
