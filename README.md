# Classificação de cogumelos: comestível ou venenoso?

O objetivo desse projeto é, dada uma base de dados com informações sobre cogumelos, prever se eles são comestíveis ou venenosos. 

A base de dados utilizada nesse projeto pode ser encontrada aqui: <https://www.kaggle.com/datasets/vishalpnaik/mushroom-classification-edible-or-poisonous/data>

### Exploração de Dados

- Carregamento do Dataset: O conjunto de dados é carregado e suas dimensões e as primeiras linhas são visualizadas para entender a estrutura dos dados.

- Análise Exploratória: As características dos cogumelos são descritas e visualizadas. Isso inclui a distribuição das variáveis numéricas e a contagem de classes para as variáveis categóricas.

### Modelagem

- Modelos Utilizados: XGBoost, LightGBM, CatBoost e Regressão Logística são treinados para classificar os cogumelos como comestíveis ou venenosos.
  
Os **modelos de boosting** (como XGBoost, LightGBM e CatBoost) são técnicas de aprendizado de máquina baseadas em árvores de decisão que são treinadas sequencialmente. Cada árvore tenta corrigir os erros das árvores anteriores, focando nas instâncias que foram classificadas incorretamente. Isso geralmente resulta em modelos muito poderosos, capazes de capturar padrões complexos nos dados.
- Validação Cruzada: Os modelos são avaliados usando validação cruzada. Métricas como precisão, revocação, acurácia, F1-score, precision_recall AUC e ROC AUC são calculadas para cada modelo.

A **Validação Cruzada** é essencial para avaliar a capacidade de generalização de um modelo. Ela divide o conjunto de dados em partes menores e utiliza várias combinações dessas partes para treinar e testar o modelo. Isso é crucial para evitar o overfitting do modelo aos dados de treinamento e garantir que ele possa generalizar bem para novos dados.

### Tunagem de Hiperparâmetros 
- O modelo CatBoost é selecionado para tunagem de hiperparâmetros usando a biblioteca Optuna. A precisão é maximizada como métrica de otimização.

**Maximizar a precisão** é importante neste contexto porque estamos lidando com a classificação de cogumelos como comestíveis ou venenosos. A precisão mede a proporção de previsões corretas que o modelo faz em relação ao total de previsões. Quando se trata de cogumelos venenosos, é fundamental minimizar os falsos positivos (classificar um cogumelo venenoso como comestível), pois isso pode ter sérias consequências para a saúde.

### Conclusão

Este notebook é um exemplo completo de um projeto de ciência de dados, desde a análise exploratória inicial até a modelagem, tunagem e avaliação do modelo. Ele demonstra várias etapas comuns em um projeto de aprendizado de máquina e fornece uma visão geral do processo de desenvolvimento de modelos preditivos.
