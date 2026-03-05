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
├── Untitled0.ipynb
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

O que acontece aqui

Nesta etapa são importadas as principais bibliotecas utilizadas na análise:

Pandas

Biblioteca fundamental para manipulação de dados estruturados.

Permite:

carregar datasets

limpar dados

transformar dados

realizar análises estatísticas

Matplotlib

Biblioteca utilizada para visualização de dados, permitindo criar gráficos como:

histogramas

scatterplots

boxplots

Seaborn

Biblioteca construída sobre o Matplotlib que facilita a criação de visualizações estatísticas mais sofisticadas.

2️⃣ Carregamento do Dataset
df = pd.read_csv("salario_profissionais_dados.csv")
O que acontece aqui

O dataset é carregado utilizando a função:

pd.read_csv()

Isso cria um DataFrame, que é a estrutura de dados principal do Pandas.

Um DataFrame funciona como uma tabela onde:

cada linha representa uma observação

cada coluna representa uma variável

3️⃣ Visualização Inicial dos Dados
df.head(5)
Objetivo

Visualizar as primeiras 5 linhas do dataset.

Isso permite:

verificar se o dataset foi carregado corretamente

entender a estrutura das colunas

identificar o tipo de informação disponível

4️⃣ Dimensão do Dataset
df.shape
Objetivo

Retorna a dimensão do dataset:

(linhas, colunas)

Isso ajuda a entender:

quantos registros existem

quantas variáveis estão sendo analisadas

5️⃣ Informações Gerais do Dataset
df.info()
O que essa função mostra

nome das colunas

tipo de dados de cada coluna

quantidade de valores não nulos

uso de memória

Isso é importante para identificar:

colunas numéricas

colunas categóricas

possíveis problemas de dados faltantes

6️⃣ Verificação de Valores Nulos
df.isnull().sum()
Objetivo

Identificar dados ausentes no dataset.

Valores nulos podem prejudicar análises e modelos de machine learning.

Essa etapa permite saber:

quais colunas possuem valores faltantes

quantos registros estão incompletos

7️⃣ Frequência de Combinações de Variáveis
df[['job_title', 'experience_level', 'company_size']].value_counts(normalize=True).head(10)
O que essa análise faz

Analisa as combinações mais frequentes entre:

cargo

nível de experiência

tamanho da empresa

O parâmetro:

normalize=True

transforma os valores em proporções (%).

Isso permite entender padrões como:

quais cargos aparecem mais

em quais empresas

com quais níveis de experiência

8️⃣ Estatísticas Descritivas
df.describe()
O que essa função mostra

Estatísticas básicas das variáveis numéricas:

média

desvio padrão

valor mínimo

quartis

valor máximo

Essa etapa ajuda a entender a distribuição geral dos salários e outras variáveis numéricas.

9️⃣ Distribuição dos Salários
sns.histplot(df['salary_in_usd'], kde=True)
plt.title('Distribuição de Salários em USD')
plt.show()
O que esse gráfico mostra

Um histograma da distribuição salarial.

O histograma mostra:

concentração de salários

dispersão

possíveis outliers

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

mediana salarial

quartis

dispersão

possíveis outliers

Ele permite comparar visualmente salários entre diferentes níveis de experiência.

🌍 Salário Médio por País
df.groupby('employee_residence')['salary_in_usd'].mean().sort_values(ascending=False)
Objetivo da análise

Calcular o salário médio por país de residência.

Essa análise permite identificar:

países com maiores salários

diferenças regionais na remuneração

🔗 Correlação entre Variáveis Numéricas
df[['salary_in_usd', 'work_year', 'years_of_experience']].corr()
O que é correlação

Correlação mede o grau de relação entre duas variáveis numéricas.

O valor varia entre:

-1 → correlação negativa
0 → nenhuma correlação
+1 → correlação positiva
Interpretação possível

anos de experiência podem estar positivamente relacionados ao salário

ano de trabalho pode indicar evolução do mercado ao longo do tempo

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
