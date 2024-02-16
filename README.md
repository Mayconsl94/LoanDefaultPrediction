# LoanDefaultPrediction

Esse foi o meu primeiro desafio em busca de construir um portfólio, nesse participei do Coursera Data Science Coding Challange!

Inicialmente busquei a compreensão do dataset e tipos de dados que iria trabalhar:
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/d97a46cd-7a93-4327-bd5a-c0872056a2a7)

Depois avaliei a distribuição dos dados:
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/cf929513-e970-43a8-8a89-6595716182e6)

Descartando a hipótese de dados nulos que pudessem ser problema mais a frente.
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/9dce3ac9-055e-49f6-bea8-e68bc063cebb)

Apliquei o Label encoder para transformação das variáveis categóricas. Aqui eu testei o getdummies e não havia uma grande mudança na performance do modelo então optei pelo label encoder com a escala normalizada posteriormente com MinMaxScaler.
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/2b3524f6-c49c-41fb-bdad-8910369237db)

Aplicando MinMaxScaler() e avaliando a distribuição dos dados.
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/a0e942c3-3fc4-45df-9c42-f247a632af97)

Usei uma matriz de correlação para entender a relação das variáveis. 
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/0141a832-2f28-4848-8f4e-d56d9effbfc2)

Também apliquei o método de PCA para buscar as variáveis mais representativas.
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/edab0636-5f4b-4390-a0d1-cb7027415467)
Testei a previsão usando apenas os n_components principais que explicavam 95% da variação, mas a performance foi inferior a previsão sem aplicar o PCA então acabei abandonando o uso do método.

Testei também modelos de XGBoost, Regressão Logistica, RandomForestClassifier, Regressão Linear, mas o modelo que melhor performou foi RandomForestRegressor.
Usei RandomizedSearch para encontrar os melhores hiperparâmetros e posteriormente fazer o treinamento com esses hiperparâmetros ajustados.

Separei a base em 70% treino x 30% teste. Com isso consegui na base de treino uma roc_auc_score de 74,98%.
![image](https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/8e266641-7fc3-46c8-868a-2fb8086653ea)

Submeti minha previsão para avaliação e consegui ficar entre o grupo que performou melhor do que 78% dos pares também avaliados.
<img width="262" alt="Compare Results with peers" src="https://github.com/Mayconsl94/LoanDefaultPrediction/assets/107588546/dff19dcd-e6ee-4359-be67-8bcab967ce79">
