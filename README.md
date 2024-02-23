# Code-Challenge-Advanced-Analytics

DOCUMENTO 1 NOTEBOOK: ANALISIS EXPLORATORIO DE DATOS

0.Objetivo

El principal objetivo es realizar un análisis exploratorio en el contexto de una empresa de 
seguros. Además, se debe realizar una clasificación binaria para poder predecir que pólizas 
harán un reclamo de siniestro y cuáles no.
Todo el desarrollo deberá estar hecho en Python.

Se facilitan dos datasets. El primero con información de las pólizas y el segundo con 
información de los vehículos. Ambos datasets están vinculados por el VEHICLE_ID
En este primer notebook se realizará el EDA correspondiente

1.Primera base: Vehicule info

1.1. Análisis previo de los datos

•	Se realiza la descarga
•	Se ve cuantos datos hay
•	Se ven las columnas, entendiendo si son categóricas o numéricas y que representan
Explicación de las columnas 
vehicle_info.csv
• VEHICLE_ID – Id del vehículo
• PROD_YEAR – Año de fabricación
• SEATS_NUM – Cantidad de asientos
• CARRYING_CAPACITY – Capacidad de carga
• TYPE_VEHICLE – Tipo de vehículo
• CCM_TON – Potencia del motor
• MAKE – Marca del vehículo

1.2. Valores nulos 

 Se ven los valores nulos 
Se busca realizar la imputación para que no hayan valores nulos
1.3. Revisión de la data 
Se comienza a ver que los valores tengan sentido, se realizan sus respectivos gráficos.
--Hay 10 vehículos de 1950, ¿esto está bien?
-- hay autos con 13 puestos, existen combis


2.Segunda base: insurance_data

2.1. Análisis previo de los datos

•	Se realiza la descarga
•	Se ve cuantos datos hay
•	Se ven las columnas, entendiendo si son categóricas o numéricas y que representan

Explicación de las columnas 
insurance_data.csv
• INSR_BEGIN – Fecha de inicio de la póliza
• INSR_END – Fecha de fin de la póliza
• CUSTOMER_SENIORITY – Antigüedad del cliente en la empresa
• SEX – Genero del cliente
• INSR_TYPE – Tipo de póliza
• INSURED_VALUE – Suma del valor asegurado
• PREMIUM – Cuota a pagar por la póliza
• VEHICLE_ID – Id del vehículo asegurado
• USAGE – Uso del vehículo asegurado
• CLAIM_PAID – Pago realizado al cliente por un reclamo de siniestro. Si es nulo significa que no  hubo reclamo

2.2. Valores nulos 

 Se ven los valores nulos 
Se busca realizar la imputación para que no hayan valores nulos

2.3. Revisión de la data 

Se comienza a ver que los valores tengan sentido, se realizan sus respectivos gráficos.

 -- hay valores asegurados de 0
-- hay valores premium de 0
-- hay polizas diarias?

3. Unión de la bases
   
3.1. Unión de las bases

Se realiza la unión de los datos
Se exporta la base 

3.2. Estadística descriptiva
Se realizan los gráficos y su respectiva explicación 

 
 


DOCUMENTO 2 NOTEBOOK: MODELO 

0.Objetivo

Se busca desarrollar un modelo predictivo que genere una clasificación binaria sobre las pólizas del archivo test.csv. El objetivo es poder identificar cuáles son las pólizas que realizaran un reclamo de siniestros. Se utilizarán diversas técnicas. Seleccionando las para evaluar los distintos modelos. Además, se creará el modelo justificando la elección.
Este documento corresponde a el modelo 


1.Entendiendo el problema 

Dado que se busca hacer un modelo para clasificar si hubo o no reclamos por parte de los clientes el problema es un problema de clasificación.

1.1 Data

Se trae la data previamente arreglada
Se busca ver cual seria el conjunto X y el conjunto Y 

1.1.1 Conjunto X

Se deja todo el dataset numérico
Se aplica one a las categorías 

1.1.1Conjunto Y 

Al graficarlo se evidencia que es un conjunto desbalanceado, es decir es un problema de clasificación desbalanceada

1.1.2.Division del data set en Train y test

Si bien ya se tiene un test, se debe hacer la división para poder hacer la validación cruzada y entrenar el modelo  

2.Modelos 

Se entrenan los modelos
 En este caso dado que era un problema de clasificación desbalanceado se aplican los modelos de:
Regresión logística
Regresion logística con pesos de clase
Random forest
Random forest con smote
XGB
Red neuronal( esta tiene el mejor performace pero al no poder ver seleccionar las variables mas significativas se decide utilizar el XGBOOST)

3.Selección del mejor modelo
 
XGB

4.Test

Se realiza la unión, hay 450 datos que no tienen la información del vehículo, en ese caso no se aplicara la información de los autos

4.1 Preparación del data set
Se prepara el test

4.2. Exportar resultado
•	Se le aplica el modelo
•	Se exporta el data set


