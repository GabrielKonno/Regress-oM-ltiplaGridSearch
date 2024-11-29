# Modelo de Previsão de Preços de Imóveis

## Visão Geral
Este projeto implementa um modelo de previsão de preços de imóveis utilizando técnicas de regressão múltipla e gradient boosting. O modelo analisa diversas características dos imóveis para prever preços de venda, empregando seleção de características e otimização de hiperparâmetros para maximizar o desempenho.

## Detalhes Técnicos

### Pré-processamento de Dados
- Utiliza MinMaxScaler para normalização de características
- Trata valores ausentes através de dropna()
- Implementa codificação one-hot para variáveis categóricas
- Renomeia colunas específicas para melhor legibilidade

### Processo de Desenvolvimento do Modelo
1. Regressão Linear Múltipla (MRLS)
   - Processo iterativo de seleção de características
   - Eliminação gradual de variáveis menos significativas
   - Modelo final inclui 22 características principais

2. Regressor Gradient Boosting
   - Modelo inicial com parâmetros padrão
   - Otimização de hiperparâmetros via GridSearchCV
   - Características incluídas: MSSubClass, OverallQual, OverallCond, YearBuilt, MasVnrArea, etc.

### Métricas de Desempenho do Modelo
Modelo GBR Original:
- Pontuação R²
- Erro Médio Absoluto (MAE)
- Erro Quadrático Médio (MSE)
- Raiz do Erro Quadrático Médio (RMSE)

Parâmetros do Modelo GBR Otimizado:
- Taxa de aprendizado: 0.06
- Profundidade máxima: 10
- Número de estimadores: 100
- Subamostragem: 0.2

## Requisitos
- Python 3.x
- Bibliotecas:
  - pandas
  - numpy
  - seaborn
  - scikit-learn
  - statsmodels

## Detalhes de Implementação
- Divisão Treino/Teste: 80/20
- Random state: 42
- Folds de validação cruzada GridSearch: 2
- Grade de otimização de hiperparâmetros:
  - learning_rate: [0.03, 0.04, 0.05, 0.06]
  - subsample: [0.2, 0.3, 0.4]
  - n_estimators: [100, 500, 1000, 1500]
  - max_depth: [8, 10]

## Estrutura de Arquivos
- `gridsearch_estudo2.py`: Script principal contendo desenvolvimento do modelo
- `house.xlsx`: Arquivo do conjunto de dados

## Melhorias Futuras
- Oportunidades de engenharia de características
- Expansão da validação cruzada
- Exploração de arquiteturas alternativas de modelo
- Desenvolvimento de pipeline de implantação
