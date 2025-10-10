# **Predição de Churn**

## **1\. Introdução**

O churn, também chamado de evasão de clientes, é um dos maiores desafios para empresas de telecomunicações. Ele ocorre quando um cliente decide cancelar seus serviços, impactando diretamente a receita e a sustentabilidade do negócio. Antecipar esse comportamento é fundamental para que a empresa adote estratégias preventivas de retenção, como ofertas personalizadas e melhorias no atendimento. Este projeto apresenta o desenvolvimento de um pipeline completo de machine learning para previsão de churn em uma base real de clientes, permitindo transformar dados em conhecimento acionável.

## **2\. Problema Resolvido**

A empresa de telecom analisada enfrenta dificuldades para reter clientes e sofre com uma taxa elevada de churn. O problema central que o projeto busca resolver é a identificação antecipada dos clientes com maior probabilidade de cancelar os serviços. Com essa informação, a empresa pode agir de maneira direcionada, otimizando recursos e reduzindo perdas financeiras.

## **3\. Modo de Resolução**

O projeto foi estruturado em quatro grandes etapas que se complementam. Na preparação dos dados, foi realizado o tratamento de nulos, exclusão de variáveis irrelevantes, codificação adequada para variáveis categóricas e padronização das variáveis numéricas, resultando em bases consistentes para modelagem. Em seguida, na etapa de seleção de variáveis, utilizou-se o algoritmo Random Forest para calcular a importância dos atributos, mantendo apenas aqueles mais relevantes e reduzindo a dimensionalidade do problema.

Na modelagem, foram treinados diferentes algoritmos — Árvore de Decisão, Regressão Logística, Random Forest e LightGBM — comparando o desempenho em métricas como acurácia, precisão, recall, F1-score, AUC, KS e Gini. O LightGBM se destacou pela robustez e pela melhor capacidade discriminativa. Por fim, na escoragem, o modelo campeão foi aplicado sobre toda a base de clientes, gerando probabilidades individuais de churn que podem ser utilizadas em relatórios e em estratégias de retenção.

## **4\. Estrutura do Projeto**

* **01 \- Data Prep**: O dataset bruto foi tratado para garantir qualidade e consistência. A variável alvo *Churn* foi convertida para formato binário (0/1), valores nulos foram preenchidos ou removidos, variáveis irrelevantes foram descartadas e as categóricas passaram por *Label Encoding* e *One-Hot Encoding*. Por fim, as variáveis numéricas foram padronizadas com *StandardScaler*, resultando nas bases finais **abt\_train** e **abt\_test**.  
  

* **02 \- Feature Selection**: Com os dados prontos, foi aplicada a técnica de seleção de variáveis usando a importância de atributos do **Random Forest**. Apenas as variáveis com relevância maior que 10% da máxima foram mantidas. Também foi analisada a correlação entre as variáveis selecionadas para evitar redundância. O resultado foi um conjunto mais enxuto, contendo apenas os atributos mais significativos.  
    
* **03 \- Modelagem**: Quatro algoritmos foram treinados e avaliados: **Árvore de Decisão, Regressão Logística, Random Forest e LightGBM**. Cada modelo foi comparado por métricas como AUC, KS, Gini, precisão, recall e F1-score. O **LightGBM** se destacou como o modelo campeão, equilibrando melhor poder preditivo, robustez e generalização, e foi salvo para uso posterior.

* **04 \- Escoragem**: O modelo campeão (LightGBM) foi aplicado em 100% da base preparada. Foram geradas as probabilidades individuais de churn (*score\_1*) e a classificação final (*class*) para cada cliente. Os resultados foram exportados em CSV, prontos para apoiar estratégias de retenção e tomada de decisão pela empresa.  
  .

## **5\. Tecnologias Usadas**

* **Linguagem:** Python

* **Bibliotecas principais:**

  * pandas, numpy → manipulação e análise de dados

  * scikit-learn → pré-processamento, modelagem e métricas

  * lightgbm → modelo de boosting de gradiente eficiente

  * matplotlib, seaborn → visualização e análise gráfica

* **Ambiente:** Google Colab / Jupyter Notebook

## **6\. Resultados**

O modelo LightGBM foi escolhido como o campeão, apresentando excelente desempenho na previsão de churn. Ele se destacou pela alta AUC, confirmando sua capacidade discriminativa, além de consistência em métricas como KS e Gini, o que indica robustez e ausência de overfitting. Outro ponto relevante foi a redução de falsos positivos, que permite direcionar ações de retenção de forma mais eficiente, evitando custos desnecessários com clientes que não apresentam risco real de cancelamento. O pipeline completo garante reprodutibilidade, já que todos os artefatos foram salvos em arquivos .pkl, e pode ser facilmente aplicado em novos conjuntos de clientes para apoiar a tomada de decisões estratégicas da empresa.

