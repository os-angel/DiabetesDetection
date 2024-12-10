# **Diabetes Prediction using Greressor Decision Tree**

## **Motivation**

Predicting diabetes using a machine learning (ML) model is crucial because it can address several important issues:

**Early Detection:** 

Identifying individuals at risk before they develop severe symptoms allows for early intervention and prevention.
Personalized Treatment: ML models can help tailor treatment plans based on individual patient characteristics.

**Cost Reduction:** 

Early prevention and treatment can significantly reduce long-term healthcare costs.
Improved Quality of Life: Preventing severe complications enables patients to maintain a better quality of life.

**Resource Optimization:** 

Healthcare systems can use resources more efficiently by focusing on high-risk patients.

# **Introduction**
In this notebook, we are going to apply a Decision Tree Regressor in a real case of diabetes prediction. We are also going to apply some performance metrics and, above all, an exploratory analysis of the data.
To make the replication of this code faster and more efficient, we are going to use the data from the sklearn.datasets library and we are going to load it into the notebook



### **Importing Libraries and data description**
# Diabetes Dataset

Ten baseline variables, including age, sex, body mass index, average blood pressure, and six blood serum measurements, were obtained for each of (n = 442) diabetes patients. Additionally, the response of interest is a quantitative measure of disease progression one year after baseline.

## Data Set Characteristics:

- **Number of Instances**: 442
- **Number of Attributes**: The first 10 columns are numeric predictive values.
- **Target**: Column 11 represents a quantitative measure of disease progression one year after baseline.

## Attribute Information:

- **age**: age in years
- **sex**: gender (binary)
- **bmi**: body mass index
- **bp**: average blood pressure
- **s1**: tc, total serum cholesterol
- **s2**: ldl, low-density lipoproteins
- **s3**: hdl, high-density lipoproteins
- **s4**: tch, total cholesterol / HDL
- **s5**: ltg, possibly log of serum triglycerides level
- **s6**: glu, blood sugar level

**Note**: Each of these 10 feature variables has been mean-centered and scaled by the standard deviation times the square root of `n_samples` (i.e., the sum of squares of each column totals 1).

## Source URL:
[Diabetes Dataset](https://www.openml.org/d/37)

For more information, see: Bradley Efron, Trevor Hastie, Iain Johnstone, and Robert Tibshirani (2004) "Least Angle Regression," *Annals of Statistics* (with discussion), 407-499. [Least Angle Regression Paper](https://projecteuclid.org/euclid.aos/1084937628)

##**Exploratory Dana Alaysis**
We will examine the distribution of the variables that make up the model, including age, BMI, and the other characteristics measured in diabetic patients.


<img width="1495" alt="Captura de pantalla 2024-12-10 a la(s) 2 05 17 p  m" src="https://github.com/user-attachments/assets/d2095209-b5f1-4d3a-988e-f4d322647327">


## **Interpretation of the Correlation Matrix**

The correlation matrix provides insights into the relationships between different variables in the dataset. Here are some key observations:

**Age:**

Shows moderate positive correlations with blood pressure (0.314) and blood sugar level (0.282). This suggests that as age increases, these variables tend to increase as well.


**Sex:**

Has a notable negative correlation with high-density lipoproteins (s3) (-0.355) and a positive correlation with total cholesterol/HDL ratio (s4) (0.320). This indicates that sex may influence these lipid measurements differently.


**BMI:** Exhibits strong positive correlations with average blood pressure (0.394), total cholesterol/HDL ratio (0.431), and blood sugar level (0.405). 

Higher BMI is associated with higher values in these health indicators.


**Blood Pressure (bp):** Correlates positively with BMI (0.394), blood sugar level (0.375), and total cholesterol/HDL ratio (0.213). This suggests a link between blood pressure and these metabolic factors.
Serum Measurements (s1 to s6):

s1 (total serum cholesterol) and s2 (LDL) have a very high correlation (0.891), indicating they often increase together.
s3 (HDL) has a strong negative correlation with s4 (-0.737), suggesting that higher HDL is associated with a lower total cholesterol/HDL ratio.
s5 (possibly log of serum triglycerides) shows strong positive correlations with BMI (0.468) and blood sugar level (0.479), indicating these factors are related to triglyceride levels.
<img width="916" alt="Captura de pantalla 2024-12-10 a la(s) 2 06 48 p  m" src="https://github.com/user-attachments/assets/d9964dde-4c33-4362-b3cc-3896ed800043">


## **Devision Tree Regressor**


This line imports the DecisionTreeRegressor class from the sklearn.tree module. This class is used to create a decision tree model for regression tasks.
Importing Evaluation Metrics:

This line imports three evaluation metrics from the sklearn.metrics module: mean_squared_error, r2_score, and mean_absolute_error. These metrics will be used to assess the performance of the regression model.
Creating the Regressor Instance:

This line creates an instance of the DecisionTreeRegressor class. The random_state=42 parameter is set to ensure that the results are reproducible by initializing the random number generator with a fixed seed.
Fitting the Model:

This line trains the decision tree regressor using the training data. The fit method takes two arguments: X_train (the training features) and y_train (the training target values). During this step, the model learns the relationship between the input features and the target variable.

<img width="731" alt="Captura de pantalla 2024-12-10 a la(s) 2 07 18 p  m" src="https://github.com/user-attachments/assets/f0d1a81e-0552-4f2f-baa3-137b96abf6a2">

##**Conclusion**
El modelo de árbol de decisión, después de la optimización de hiperparámetros, mostró una mejora en las métricas de rendimiento en comparación con el modelo inicial.  
Las métricas R², MAE y MSE proporcionan una indicación de la precisión del modelo en la predicción de la progresión de la diabetes.  
La visualización del árbol permite entender las reglas de decisión aprendidas por el modelo, mostrando las características más importantes para la predicción.  
Si bien los resultados obtenidos ofrecen un punto de partida, se recomienda explorar otros modelos o técnicas de aprendizaje automático para determinar si existen alternativas con mayor precisión o interpretabilidad.  Además, un análisis más profundo de los residuos del modelo podría revelar patrones no capturados por el modelo actual. El análisis usando herramientas de ML supervisado, suelen tener un rendimientoa ceptable para este tipo de aplicaciones.

<img width="1560" alt="Captura de pantalla 2024-12-10 a la(s) 2 07 41 p  m" src="https://github.com/user-attachments/assets/f62c51c1-4942-4055-9095-92a65d137343">














