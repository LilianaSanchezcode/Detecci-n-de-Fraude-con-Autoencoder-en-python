# Detecci-n-de-Fraude-con-Autoencoder-en-python




## **Detección de anomalías mediante Autoencoder:**

Siga los siguientes pasos para detectar anomalías en un conjunto de datos de gran dimensión. También puede aplicar esto a conjuntos de datos no balanceados. Durante el entrenamiento, ingrese solo transacciones normales en el codificador. La capa de cuello de botella aprenderá la representación latente de los datos de entrada normales. El decodificador utilizará la salida de las capas de cuello de botella para reconstruir las transacciones normales de los datos de entrada originales. Una transacción fraudulenta será diferente a una transacción normal. El Autoencoder tendrá problemas para reconstruir la transacción fraudulenta y, por lo tanto, el error de reconstrucción será alto. Puede marcar una nueva transacción como fraudulenta en función de un valor de umbral especificado para el error de reconstrucción.

**Datos:**

**Fuente: https://www.kaggle.com/mlg-ulb/creditcardfraud**

El conjunto de datos contiene transacciones realizadas con tarjetas de crédito en septiembre de 2013 por titulares de tarjetas europeos. Este conjunto de datos presenta transacciones que ocurrieron en dos días, donde tenemos 492 fraudes de 284.807 transacciones. El conjunto de datos está muy desequilibrado, la clase positiva (fraudes) representa el 0,172% de todas las transacciones.
Contiene solo variables de entrada numéricas que son el resultado de una transformación PCA. Desafortunadamente, debido a problemas de confidencialidad, no podemos proporcionar las características originales y más información de fondo sobre los datos. Las características V1, V2,… V28 son los componentes principales obtenidos con PCA, las únicas características que no se han transformado con PCA son 'Tiempo' y 'Cantidad'. La característica 'Tiempo' contiene los segundos transcurridos entre cada transacción y la primera transacción en el conjunto de datos. La función 'Importe' es el Importe de la transacción, esta función se puede utilizar para el aprendizaje dependiente de los costos por ejemplo. La característica 'Clase' es la variable de respuesta y toma el valor 1 en caso de fraude y 0 en caso contrario.
Dada la relación de desequilibrio de clases, recomendamos medir la precisión utilizando el área bajo la curva de recuperación de precisión (AUPRC). La precisión de la matriz de confusión no es significativa para la clasificación desequilibrada
________________________________________
**Variables no anonimizadas:**


- Time Contiene los segundos transcurridos entre cada transacción.
- Amount - Valor total de la transacción.
- Class-Es el target, etiqueta dada a las transacciones, donde 0 representa una transacción normal y 1 refiere a una transacción fraudulenta.
 

## Este proyecto tratará los siguientes puntos:


- Desarrollo de modelo de aprendizaje No supervisado:Autoencoder


- Evaluación del rendimiento del modelo mediante:


  - Curva ROC


  - Matriz de confusión

 ## **Hallazgos:**

El codificador automático ha aprendido a discriminar anomalías.Se ha clasificado correctamente a 79 de los 98 casos fradulentos, lo que representa el 81% del total de los casos. Sin embargo, al mismo tiempo, se ha clasificado erróneamente 1254 casos como fradulentos (son normales), esto representa el 2,2 % de los casos normales, lo que podria provocar insatisfacción en el cliente.

