# Analise_Exploratoria_de_Salarios_na_Area_de_Dados
Este projeto realiza uma Análise Exploratória de Dados (EDA) utilizando Python para investigar padrões salariais de profissionais da área de dados.

Análise Exploratória de Salários na Área de Dados

📌 Sobre o Projeto

Este projeto realiza uma Análise Exploratória de Dados (EDA) utilizando Python para investigar padrões salariais de profissionais da área de dados.

O objetivo da análise é compreender como fatores como:

- Nível de experiência

- País de residência

- Cargo

- Tamanho da empresa

Influenciam os salários pagos na indústria de dados.

A análise foi realizada utilizando Python e bibliotecas de ciência de dados, explorando estatísticas descritivas, distribuições e relações entre variáveis.

🧠 Tecnologias Utilizadas

- Python

- Pandas

- Matplotlib

- Seaborn

- Jupyter Notebook

📂 Estrutura do Projeto

data-salary-analysis/

│

├── analisedesalario.ipynb

├── salario_profissionais_dados.csv

└── README.md

📊 Dataset

O dataset utilizado contém informações sobre profissionais da área de dados, incluindo:

- Cargo ocupado (job_title)

- Nível de experiência (experience_level)

- País de residência (employee_residence)

- Tamanho da empresa (company_size)

- Salário (salary_in_usd)

- Anos de experiência

- Ano de trabalho

🔎 Etapas da Análise

1️⃣ Importação das bibliotecas

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

# O que acontece aqui

Nesta etapa são importadas as principais bibliotecas utilizadas na análise:

# Pandas

Biblioteca fundamental para manipulação de dados estruturados.

Permite:

- Carregar datasets

- Limpar dados

- Transformar dados

- Realizar análises estatísticas

# Matplotlib

Biblioteca utilizada para visualização de dados, permitindo criar gráficos como:

- Histogramas

- Scatterplots

- Boxplots

# Seaborn

Biblioteca construída sobre o Matplotlib que facilita a criação de visualizações estatísticas mais sofisticadas.

2️⃣ Carregamento do Dataset

df = pd.read_csv("salario_profissionais_dados.csv")

# O que acontece aqui

O dataset é carregado utilizando a função:

pd.read_csv()

Isso cria um DataFrame, que é a estrutura de dados principal do Pandas.

Um DataFrame funciona como uma tabela onde:

- Cada linha representa uma observação

- Cada coluna representa uma variável

3️⃣ Visualização Inicial dos Dados

df.head(5)

Objetivo

Visualizar as primeiras 5 linhas do dataset.

Isso permite:

- Verificar se o dataset foi carregado corretamente

- Entender a estrutura das colunas

- Identificar o tipo de informação disponível

4️⃣ Dimensão do Dataset

df.shape

Objetivo

Retorna a dimensão do dataset:

(linhas, colunas)

Isso ajuda a entender:

- Quantos registros existem

- Quantas variáveis estão sendo analisadas

5️⃣ Informações Gerais do Dataset

df.info()

O que essa função mostra:

- Nome das colunas

- Tipo de dados de cada coluna

- Quantidade de valores não nulos

- Uso de memória

Isso é importante para identificar:

- Colunas numéricas

- Colunas categóricas

- Possíveis problemas de dados faltantes

6️⃣ Verificação de Valores Nulos

df.isnull().sum()

Objetivo

Identificar dados ausentes no dataset.

Valores nulos podem prejudicar análises e modelos de machine learning.

Essa etapa permite saber:

- Quais colunas possuem valores faltantes

- Quantos registros estão incompletos

7️⃣ Frequência de Combinações de Variáveis

df[['job_title', 'experience_level', 'company_size']].value_counts(normalize=True).head(10)

O que essa análise faz

Analisa as combinações mais frequentes entre:

- Cargo

- Nível de experiência

- Tamanho da empresa

O parâmetro:

normalize=True

transforma os valores em proporções (%).

Isso permite entender padrões como:

- Quais cargos aparecem mais

- Em quais empresas

- Com quais níveis de experiência

8️⃣ Estatísticas Descritivas

df.describe()

O que essa função mostra

Estatísticas básicas das variáveis numéricas:

- Média

- Desvio padrão

- Valor mínimo

- Quartis

- Valor máximo

Essa etapa ajuda a entender a distribuição geral dos salários e outras variáveis numéricas.

9️⃣ Distribuição dos Salários

sns.histplot(df['salary_in_usd'], kde=True)

plt.title('Distribuição de Salários em USD')

plt.show()

O que esse gráfico mostra

Um histograma da distribuição salarial.

O histograma mostra:

- Concentração de salários

- Dispersão

- Possíveis outliers

O parâmetro:

kde=True

adiciona uma curva de densidade, facilitando a visualização da distribuição.

🔟 Salário Médio por Nível de Experiência

media_experiencia = df.groupby('experience_level')['salary_in_usd'].mean().sort_values()

O que essa análise faz

Agrupa os dados por nível de experiência e calcula o salário médio para cada grupo.

Isso permite entender como a experiência impacta os salários.

📦 Boxplot de Salários por Experiência

sns.boxplot(x='experience_level', y='salary_in_usd', data=df)

O que o boxplot mostra

O boxplot apresenta:

- Mediana salarial

- Quartis

- Dispersão

- Possíveis outliers

Ele permite comparar visualmente salários entre diferentes níveis de experiência.

🌍 Salário Médio por País

df.groupby('employee_residence')['salary_in_usd'].mean().sort_values(ascending=False)

Objetivo da análise

Calcular o salário médio por país de residência.

Essa análise permite identificar:

- Países com maiores salários

- Diferenças regionais na remuneração

🔗 Correlação entre Variáveis Numéricas

df[['salary_in_usd', 'work_year', 'years_of_experience']].corr()

O que é correlação

Correlação mede o grau de relação entre duas variáveis numéricas.

O valor varia entre:

-1 → correlação negativa
0 → nenhuma correlação
+1 → correlação positiva
Interpretação possível

- Anos de experiência podem estar positivamente relacionados ao salário

- Ano de trabalho pode indicar evolução do mercado ao longo do tempo

📈 Principais Insights Possíveis

A análise pode revelar padrões como:

- Salários aumentam conforme a experiência

- Determinados países pagam salários mais altos

- Grandes empresas tendem a oferecer melhores salários

- A distribuição salarial apresenta grande variabilidade

🚀 Possíveis Melhorias Futuras

- Análise por cargo específico

- Regressão para previsão salarial

- Clusterização de perfis profissionais

- Análise de tendência temporal de salários

- Dashboards interativos
