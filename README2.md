# Trabalho Final - Inteligência Computacional

Trabalho da disciplina de Inteligência Computacional do curso de Ciência de Dados da Fatec Jundiaí.

## Sobre o projeto

A ideia foi usar dados climáticos de 190 capitais do mundo pra tentar classificar em qual grupo de renda do Banco Mundial cada país se encaixa (Low, LowerMid, UpperMid, High).

O dataset veio do Kaggle e tem dados da NASA coletados entre 1990 e 2024, com informações de temperatura, precipitação, vento, radiação solar, entre outras.

## Dataset

- **Nome:** NASA POWER Climate Risk Indices - 190 Capitals (1990-2024)
- **Fonte:** Kaggle
- **Linhas:** 6650
- **Colunas:** 56
- **Problema:** Classificação multiclasse
- **Target:** `wb_income_group`

O dataset tem valores ausentes em algumas colunas e variáveis categóricas, então precisou de bastante pré-processamento.

## O que foi feito

- Análise exploratória com histogramas, boxplots, scatterplot e heatmap
- Tratamento de valores nulos com SimpleImputer (mediana pra numéricas, moda pra categóricas)
- Codificação das variáveis categóricas com OneHotEncoder
- Escalonamento com StandardScaler
- Criação de 2 novas features (engenharia de atributos)
- Pipeline com ColumnTransformer pra evitar data leakage
- K-Fold Cross Validation com k=5
- GridSearchCV pra otimizar os hiperparâmetros do KNN
- Avaliação com acurácia e matriz de confusão

## Resultados

Os resultados detalhados estão no notebook. O modelo KNN com os melhores parâmetros encontrados pelo GridSearchCV conseguiu uma acurácia razoável considerando que só usamos variáveis climáticas.

## Conclusão

O pré-processamento foi a parte mais trabalhosa e importante do projeto. O pipeline ajudou bastante a organizar o fluxo e garantir que não houvesse data leakage. Variáveis climáticas sozinhas não explicam tudo sobre o nível de renda de um país, mas conseguem capturar alguns padrões interessantes.

## Arquivos

```
├── notebook_inteligencia_computacional.ipynb
├── nasa_power_climate_risk_indices_190_capitals_1990_2024.csv
└── README.md
```

## Tecnologias

- Python 3
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
