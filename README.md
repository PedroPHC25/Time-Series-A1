# Análise de Séries Temporais - Volume Semanal

Este repositório contém uma análise completa de séries temporais aplicada a dados de volume semanal, desenvolvida como parte de um projeto acadêmico da disciplina de Séries Temporais.

## Descrição do Projeto

O projeto realiza uma análise detalhada de uma série temporal de volume semanal, explorando diferentes técnicas de modelagem e previsão:

- **Decomposição sazonal** para identificar tendências e padrões
- **Modelos baseline** para estabelecer benchmarks de desempenho
- **Regressão linear múltipla** com diferentes covariáveis
- **Análise de resíduos** para validação dos modelos

### Dependências Principais

- `pandas` - Manipulação de dados
- `numpy` - Operações numéricas
- `matplotlib` - Visualização de dados
- `statsmodels` - Modelagem estatística e análise de séries temporais
- `scikit-learn` - Métricas de avaliação
- `scipy` - Funções estatísticas

## Metodologia

### 1. Análise Exploratória

- Visualização da série temporal
- Análise de autocorrelação (ACF)
- Decomposição sazonal (períodos de 4 e 52 semanas)
- Avaliação de tendência e sazonalidade

### 2. Modelos Baseline

Foram implementados quatro modelos baseline:

- **Média**: Previsão baseada na média histórica
- **Random Walk (Ingênuo)**: Último valor observado
- **Random Walk with Drift**: Incorpora tendência linear
- **Ingênuo Sazonal**: Considera sazonalidade de 52 semanas

### 3. Regressão Linear Múltipla

Covariáveis testadas:

- **Tendência**: Covariável temporal linear
- **Dummies mensais**: Indicadoras para cada mês
- **Lags**: Valores defasados (1, 4 e 12 semanas)
- **Médias Móveis**: Simples e exponenciais (4 e 12 semanas)
- **Volatilidade**: Desvio padrão móvel (4 e 12 semanas)

### 4. Métricas de Avaliação

#### Métricas Pontuais:
- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)
- **MAPE** (Mean Absolute Percentage Error)
- **MASE** (Mean Absolute Scaled Error)

#### Métricas Distribucionais:
- **Winkler Score**: Avalia intervalos de previsão
- **Quantile Score**: Precisão em quantis específicos
- **CRPS** (Continuous Ranked Probability Score)

## Principais Resultados

### Análise da Série

- **Tendência**: Forte evidência de tendência crescente
- **Sazonalidade**: Não foi identificada sazonalidade significativa
- **Transformação**: Modelo logarítmico apresentou melhor ajuste (R² = 0.814)

### Melhor Modelo

O modelo de **Lags** apresentou o melhor desempenho geral:
- Excelente MAPE e baixa média de resíduos
- Boa captura da dependência temporal
- Resíduos bem comportados (ACF próximo de ruído branco)

### Comparação de Desempenho

Os modelos de **Regressão Linear Múltipla** superaram significativamente os baselines, com destaque para:
1. Modelo de Lags
2. Médias Móveis
3. Lags + Médias Móveis

## Como Usar

1. Abra o notebook principal:
```bash
jupyter notebook relatorio.ipynb
```

2. Execute as células sequencialmente para:
   - Carregar e visualizar os dados
   - Realizar análise exploratória
   - Treinar modelos baseline
   - Ajustar modelos de regressão linear
   - Avaliar e comparar resultados
   - Analisar resíduos

## 👥 Contribuidores

Pedro Henrique Coterli, Kauan Mariani Ferreira, Matheus Fillype Ferreira de Carvalho, Sillas Rocha da Costa, Gustavo Tironi, Lívia Verly
