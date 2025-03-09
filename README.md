# Previsão da Qualidade do Vinho

## Visão Geral do Projeto

Este projeto teve como objetivo desenvolver um modelo de classificação para prever a qualidade de vinhos tintos e brancos com base em seus atributos físico-químicos. O pipeline completo de aprendizado de máquina foi implementado, desde a análise exploratória de dados (EDA) até a avaliação e otimização de modelos de classificação. O dataset utilizado foi o **Wine Quality Dataset**, disponível no repositório da UCI Machine Learning Repository.

## Dataset

O dataset contém informações sobre vinhos tintos e brancos, com características físico-químicas como acidez, pH, densidade e uma variável de qualidade avaliada por especialistas. A variável alvo foi transformada em uma classificação binária:

- **Qualidade alta**: `quality >= 7` → Classe 1
- **Qualidade baixa**: `quality < 7` → Classe 0

### Links para o Dataset:
- [Wine Quality Dataset](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)
- Arquivos utilizados:
  - `winequality-red.csv` (vinhos tintos)
  - `winequality-white.csv` (vinhos brancos)

## Etapas do Projeto

### 1. Análise Exploratória de Dados (EDA)
- Os dados foram carregados utilizando a biblioteca `pandas`.
- Foram realizadas análises iniciais, como a visualização das primeiras linhas do dataset, verificação de dimensões e detecção de valores ausentes.
- Gráficos foram criados para entender a distribuição da qualidade dos vinhos e as relações entre as variáveis físico-químicas. Alguns exemplos incluem:
  - Gráficos de dispersão (ex.: `alcohol` vs `quality`).
  - Boxplots para comparar variáveis como `density` entre vinhos de qualidade alta e baixa.

### 2. Pré-processamento
- A variável `quality` foi convertida em uma classificação binária (0 ou 1).
- As variáveis contínuas foram normalizadas para garantir escalas uniformes.
- O dataset foi dividido em conjuntos de treino (80%) e teste (20%) utilizando a função `train_test_split` do `sklearn`.

### 3. Treinamento de Modelos
Três modelos de classificação foram treinados e avaliados:
1. **Regressão Logística**
2. **Random Forest**
3. **Support Vector Machine (SVM)**

Cada modelo foi treinado utilizando o conjunto de treino e avaliado no conjunto de teste.

### 4. Avaliação dos Modelos
- As métricas de desempenho calculadas para cada modelo foram:
  - **Acurácia**
  - **Precisão**
  - **Revocação**
  - **F1-Score**
- As matrizes de confusão foram construídas para analisar os erros de classificação.
- A curva **ROC-AUC** foi utilizada para comparar o desempenho dos modelos.

### 5. Otimização dos Modelos
- Foram utilizadas técnicas de busca em grade (`GridSearchCV`) para encontrar os melhores hiperparâmetros para cada modelo.
- Os resultados dos modelos foram comparados antes e depois da otimização, mostrando melhorias significativas no desempenho.

### 6. Interpretação dos Resultados
- O modelo que obteve o melhor desempenho foi o **Random Forest**, devido à sua capacidade de lidar com relações não lineares entre as variáveis.
- As variáveis físico-químicas que mais influenciaram na predição da qualidade foram **alcohol**, **volatile acidity** e **sulphates**.
- Foram identificadas possíveis melhorias, como a inclusão de mais dados ou a utilização de técnicas de ensemble para aumentar a precisão do modelo.

## Resultados e Conclusões

O projeto foi concluído com sucesso, e os modelos foram capazes de prever a qualidade dos vinhos com boa precisão. O **Random Forest** se destacou como o melhor modelo, alcançando a maior acurácia e F1-Score. A análise exploratória e a otimização dos hiperparâmetros foram etapas cruciais para o sucesso do projeto.

## Estrutura do Repositório

- **notebooks/**: Contém o notebook Python com todo o código, análises e visualizações.
- **data/**: Armazena os arquivos do dataset (`winequality-red.csv` e `winequality-white.csv`).
- **README.md**: Este arquivo, com a documentação do projeto.

## Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone git@github.com:diegoCBorba/analise-qualidade-vinho.git
   ```
2. Instale as dependências necessárias:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Execute o notebook Jupyter localizado na pasta `notebooks/` para reproduzir as análises e resultados.

## Recursos Utilizados

- **Linguagem**: Python
- **Bibliotecas**:
  - `pandas`, `numpy` para manipulação de dados.
  - `matplotlib`, `seaborn` para visualizações.
  - `sklearn` para modelagem e avaliação.
