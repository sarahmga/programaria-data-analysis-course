# Notebook – Análise de Dados 
 
Contém o arquivo Jupyter Notebook desenvolvido durante o curso da Programaria, com base na pesquisa State of Data 2022 conduzida pelo Data Hackers. O notebook cobre as etapas fundamentais de um pipeline de análise de dados, desde a leitura da base bruta até a visualização dos resultados.
 
---
 
## Seção 1 – Exploração inicial
 
Leitura da planilha com `pd.read_excel()` e inspeção geral da base antes de qualquer transformação. Funções utilizadas:
 
- `head()` e `tail()`: visualização das primeiras e últimas linhas.
- `shape`: dimensões da tabela (linhas x colunas).
- `info()`: tipos de dados, contagem de não-nulos e uso de memória.
- `describe()`: estatísticas descritivas das colunas numéricas.
---
 
## Seção 2 – Filtragem e agrupamento
 
Aplicação de filtros booleanos simples e compostos, equivalentes às análises feitas anteriormente em Excel, agora com pandas.
 
- Filtragem por igualdade, desigualdade e conteúdo textual parcial com `str.contains()`.
- Filtros numéricos e combinados com os operadores `&` e `|`.
- Contagem de valores únicos com `unique()` e `value_counts()`.
- Agrupamentos com `groupby()` e contagem de IDs únicos com `nunique()`.
- Tabela dinâmica com `pd.pivot_table()`.
---
 
## Seção 3 – Estatística descritiva
 
Cálculo das principais medidas de tendência central e dispersão, primeiro com NumPy em listas simples e depois aplicado diretamente nas colunas do DataFrame.
 
- **Média** (`np.mean()`, `.mean()`): sensível a valores extremos.
- **Mediana** (`np.median()`, `.median()`): resistente a outliers.
- **Moda** (`.mode()`): valor mais frequente.
- **Desvio padrão** (`.std()`): mede a dispersão em relação à média.
- **Mínimo e máximo** (`.min()`, `.max()`).
- Comparação de médias salariais e de idade entre gêneros.
---
 
## Seção 4 – Tratamento de valores nulos
 
Identificação e preenchimento de nulos com estratégias adequadas a cada coluna.
 
- `isnull()` e `value_counts()` para mapear os nulos existentes.
- Coluna **GENERO**: nulos preenchidos com `fillna('Prefiro não informar')`.
- Coluna **IDADE**: preenchimento segmentado pela faixa etária. Média da faixa 17-21 para os registros correspondentes e média geral para a faixa 55+, usando `loc[]` para localização precisa.
- Coluna **SALARIO**: preenchimento pela mediana geral, por ser menos sensível a valores extremos do que a média.
---
 
## Seção 5 – Detecção e tratamento de outliers
 
Identificação de valores discrepantes por dois métodos e substituição por médias segmentadas.
 
- **Método do desvio padrão**: limite superior calculado como média + 3σ.
- **Método IQR**: limites calculados como Q1 : 1,5×IQR e Q3 + 1,5×IQR.
- Visualização com `plt.boxplot()` antes e após o tratamento.
- Substituição dos outliers pela média dos registros sem outliers dentro de cada faixa salarial, preservando a coerência entre salário declarado e faixa escolhida pelo respondente.
---
 
## Seção 6 – Intervalo de confiança
 
Estimativa da faixa provável para a média salarial da população de profissionais de dados no Brasil, com base na amostra da pesquisa.
 
- Erro padrão calculado com `stats.sem()`.
- Intervalo de confiança de 95% calculado com `stats.t.interval()` da biblioteca `scipy.stats`.
- Resultado: com 95% de confiança, a média salarial está entre R$ 9.655 e R$ 10.153.
---
 
## Seção 7 – Feature engineering
 
Criação de novas colunas a partir das variáveis existentes para enriquecer a análise.
 
- **NOVO_NIVEL**: unifica gestores em uma categoria própria, usando `apply()` com função customizada e `lambda`.
- **Codificação dummy**: transformação da coluna NIVEL em colunas binárias com `pd.get_dummies()`, adequada para uso em modelos de machine learning.
- **GERACAO**: classifica cada respondente por geração (Z, Millennial, X) com base na idade.
- **EM_BUSCA** e **ABERTO_OPORTUNIDADES**: indicadores binários criados com `str.contains()` a partir da coluna de intenção de mudança de emprego.
- **ETNIA**: simplificação das categorias de cor/raça em três grupos (Branca, Não Branca, Outra).
- Merge com segunda tabela usando `pd.merge()` com `how='left'` pela chave ID.
---
 
## Seção 8 – Correlação
 
Medição da força de associação entre pares de variáveis, com método escolhido de acordo com o tipo de dado.
 
- **Pearson** (`.corr()`): para variáveis contínuas. Correlação entre idade e salário resultou em 0,29. Positiva, porém fraca.
- **Cramér's V**: para variáveis categóricas, implementado com função customizada usando `pd.crosstab()` e `chi2_contingency()` do `scipy.stats`. Correlação entre etnia e nível de ensino próxima de zero.
---
 
## Seção 9 – Integração com SQL
 
Conexão a banco de dados SQLite para cruzar os dados da pesquisa com índices socioeconômicos municipais brasileiros.
 
- Conexão com `sqlite3.connect()` e leitura com `pd.read_sql()`.
- Queries com `INNER JOIN` e `GROUP BY` para calcular a média de renda e educação por estado.
- Queries parametrizadas com placeholders `?` para evitar SQL injection.
- Merge dos resultados com o DataFrame principal e cálculo de correlação entre salário e índices de renda e educação por estado.
---
 
## Seção 10 – Visualização de dados
 
Criação de gráficos com três bibliotecas, cada uma com características distintas.
 
- **Matplotlib**: gráfico de barras com `plt.bar()` e scatter plot com `plt.scatter()`. Controle manual de título, eixos, grade e tamanho da figura.
- **Seaborn**: gráfico de contagem com `sns.countplot()`, com paleta de cores e grade configuráveis.
- **Plotly**: gráficos interativos de linha com `px.line()` e dispersão com `px.scatter()`, com suporte a marcadores e zoom.
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

