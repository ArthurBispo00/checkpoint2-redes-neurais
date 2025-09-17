# Checkpoint 2 - Treinamento de Redes Neurais com Keras

Este repositório contém a resolução da atividade de Treinamento de Redes Neurais com Keras para dados tabulares, da disciplina de Arquiteturas Disruptivas.

O código completo dos experimentos está no arquivo `exercicios_keras.ipynb.ipynb`.

### Como Rodar os Experimentos

O projeto foi desenvolvido utilizando o Google Colab e os dados foram carregados diretamente na sessão. Para replicar os resultados, siga os passos abaixo:

**1. Pré-requisitos:**
* Uma conta Google para acessar o [Google Colab](https://colab.research.google.com/). Nenhuma instalação local é necessária.

**2. Obtenção dos Dados:**
* **Wine Dataset:** Faça o download do arquivo `wine.data` a partir do [Repositório UCI Machine Learning](https://archive.ics.uci.edu/ml/machine-learning-databases/wine/).
* **California Housing Dataset:** Faça o download do arquivo `cal_housing.data` a partir do [Repositório StatLib da Carnegie Mellon](http://lib.stat.cmu.edu/datasets/houses.zip). (Este link baixa um .zip, extraia o `cal_housing.data` de dentro).

**3. Execução:**
1.  Abra o arquivo `.ipynb` deste repositório no Google Colab.
2.  No menu à esquerda, clique no ícone de **Pasta** para abrir o painel de arquivos.
3.  Clique no ícone de **Upload** (uma página com uma seta para cima) e suba os dois arquivos que você baixou: `wine.data` e `cal_housing.data`.
4.  Com os arquivos na sessão, execute todas as células do notebook em ordem, de cima para baixo, usando "Shift + Enter" ou o botão de "Play".

---

### Exercício 1 – Classificação Multiclasse (Wine Dataset)

**Objetivo:** Treinar uma rede neural para classificar vinhos em 3 classes e comparar seu desempenho com um modelo do Scikit-learn.

**Modelos Utilizados:**
1.  Rede Neural (Keras) com 2 camadas ocultas de 32 neurônios.
2.  RandomForestClassifier (Scikit-learn) com 100 estimadores.

**Resultados:**
* **Acurácia da Rede Neural:** 100.00%
* **Acurácia do RandomForestClassifier:** 100.00%

**Discussão:**

Para a tarefa de classificação do Wine Dataset, tanto a Rede Neural construída com Keras quanto o modelo RandomForestClassifier do Scikit-learn alcançaram uma acurácia perfeita de 100.00% no conjunto de teste.

Apesar do desempenho idêntico na métrica final, a análise do processo revela diferenças importantes. O RandomForestClassifier se mostrou uma solução mais simples e direta, exigindo menos pré-processamento dos dados e um tempo de treinamento significativamente menor.

Por outro lado, a Rede Neural, embora igualmente eficaz, demandou uma implementação mais complexa, incluindo a padronização dos dados e a codificação one-hot dos rótulos. A análise do histórico de treinamento também indicou um leve sinal de overfitting, onde o modelo se ajustou perfeitamente aos dados de treino em detrimento da generalização, um risco que precisa ser monitorado em arquiteturas de deep learning.

Resultado:

Para este dataset tabular específico, o `RandomForestClassifier` foi o modelo superior em termos de simplicidade e eficiência, entregando o mesmo resultado de ponta com menos esforço de implementação.

---

### Exercício 2 – Regressão (California Housing Dataset)

**Objetivo:** Treinar uma rede neural para prever o valor médio das casas e comparar seu desempenho com um modelo do Scikit-learn.

**Modelos Utilizados:**
1.  Rede Neural (Keras) com 3 camadas ocultas (64, 32, 16 neurônios).
2.  RandomForestRegressor (Scikit-learn) com 100 estimadores.

**Resultados (Erro Médio Absoluto - MAE):**
* **MAE da Rede Neural:** ~$46,525.62
* **MAE do RandomForestRegressor:** $31,971.65

**Discussão:**
Para a tarefa de regressão de previsão dos preços de imóveis no dataset da Califórnia, foram comparados uma Rede Neural (Keras) e um modelo RandomForestRegressor (Scikit-learn).

As métricas de erro mostraram um vencedor claro. O RandomForestRegressor alcançou um Erro Médio Absoluto (MAE) de $31,971.65. 

Enquanto a Rede Neural obteve um MAE de aproximadamente $46,525.62. 

Isso indica que o modelo de Random Forest foi significativamente mais preciso, com um erro médio de previsão quase $15.000 inferior.

Além da performance superior, o RandomForestRegressor também se provou uma solução mais eficiente, com menor complexidade de código, sem necessidade de pré-processamento de scaling e com tempo de treinamento muito inferior. A Rede Neural, por sua vez, apresentou um bom processo de aprendizado sem sinais de overfitting, mas não foi capaz de atingir o mesmo nível de precisão do modelo clássico de Machine Learning.

Conclusão: Para este dataset tabular de regressão, o `RandomForestRegressor` demonstrou ser o modelo superior tanto em performance (menor erro) quanto em eficiência de implementação.
