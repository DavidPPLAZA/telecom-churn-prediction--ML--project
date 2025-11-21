# PRACTICA-APRENDIZAJE-AUTOM-TICO-DAVID-JORGE-

README - Análisis de Churn de Clientes de Telecomunicaciones

## Origen del Dataset: 

El dataset utilizado es "Telco Customer Churn", disponible en Kaggle en el siguiente enlace:
https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset/data

Se trata de un conjunto de datos clásico y muy utilizado en la comunidad de Data Science, creado originalmente por IBM y posteriormente compartido en múltiples plataformas. El dataset tiene registros de clientes de una compañía de telecomunicaciones ficticia (ubicada en California) con información detallada sobre demografía, servicios contratados, tipo de contrato, facturación y comportamiento de pago.

## Descripción de columnas (procedente del link de kaggle):

7043 observaciones con 33 variables

| Columna | Descripción |
| :--- | :--- |
| **CustomerID** | Un ID único que identifica a cada cliente. |
| **Count** | Un valor utilizado en la elaboración de informes/paneles para sumar el número de clientes en un conjunto filtrado. |
| **Country** | El país de residencia principal del cliente. |
| **State** | El estado de residencia principal del cliente. |
| **City** | La ciudad de residencia principal del cliente. |
| **Zip Code** | El código postal de residencia principal del cliente. |
| **Lat Long** | La latitud y longitud combinadas de la residencia principal del cliente. |
| **Latitude** | La latitud de la residencia principal del cliente. |
| **Longitude** | La longitud de la residencia principal del cliente. |
| **Gender** | El género del cliente: Hombre, Mujer. |
| **Senior Citizen** | Indica si el cliente tiene 65 años o más: Sí, No. |
| **Partner** | Indica si el cliente tiene pareja: Sí, No. |
| **Dependents** | Indica si el cliente vive con alguna persona dependiente: Sí, No. Los dependientes podrían ser hijos, padres, abuelos, etc. |
| **Tenure Months** | Indica la cantidad total de meses que el cliente ha estado con la compañía al final del trimestre especificado anteriormente. |
| **Phone Service** | Indica si el cliente se suscribe al servicio telefónico residencial de la compañía: Sí, No. |
| **Multiple Lines** | Indica si el cliente se suscribe a múltiples líneas telefónicas con la compañía: Sí, No. |
| **Internet Service** | Indica si el cliente se suscribe al servicio de Internet con la compañía: No, DSL, Fibra Óptica, Cable. |
| **Online Security** | Indica si el cliente se suscribe a un servicio adicional de seguridad en línea proporcionado por la compañía: Sí, No. |
| **Online Backup** | Indica si el cliente se suscribe a un servicio adicional de copia de seguridad en línea proporcionado por la compañía: Sí, No. |
| **Device Protection** | Indica si el cliente se suscribe a un plan adicional de protección de dispositivos para su equipo de Internet proporcionado por la compañía: Sí, No. |
| **Tech Support** | Indica si el cliente se suscribe a un plan adicional de soporte técnico de la compañía con tiempos de espera reducidos: Sí, No. |
| **Streaming TV** | Indica si el cliente utiliza su servicio de Internet para transmitir programación de televisión de un proveedor externo: Sí, No. La compañía no cobra una tarifa adicional por este servicio. |
| **Streaming Movies** | Indica si el cliente utiliza su servicio de Internet para transmitir películas de un proveedor externo: Sí, No. La compañía no cobra una tarifa adicional por este servicio. |
| **Contract** | Indica el tipo de contrato actual del cliente: Mes a mes, Un año, Dos años. |
| **Paperless Billing** | Indica si el cliente ha elegido la facturación sin papel: Sí, No. |
| **Payment Method** | Indica cómo paga el cliente su factura: Retiro Bancario, Tarjeta de Crédito, Cheque Enviado por Correo. |
| **Monthly Charge** | Indica el cargo mensual total actual del cliente por todos sus servicios de la compañía. |
| **Total Charges** | Indica los cargos totales del cliente, calculados hasta el final del trimestre especificado anteriormente. |
| **Churn Label** | Sí = el cliente abandonó la compañía este trimestre. No = el cliente permaneció en la compañía. Directamente relacionado con Churn Value. |
| **Churn Value** | 1 = el cliente abandonó la compañía este trimestre. 0 = el cliente permaneció en la compañía. Directamente relacionado con Churn Label. |
| **Churn Score** | Un valor de 0 a 100 que se calcula utilizando la herramienta predictiva IBM SPSS Modeler. El modelo incorpora múltiples factores conocidos que causan la deserción. Cuanto mayor sea la puntuación, más probable es que el cliente abandone. |
| **CLTV** | Valor de por vida del cliente (Customer Lifetime Value). El CLTV predicho se calcula utilizando fórmulas corporativas y datos existentes. Cuanto mayor sea el valor, más valioso es el cliente. Los clientes de alto valor deben ser monitoreados para la deserción. |
| **Churn Reason** | Una razón específica del cliente para dejar la compañía. Directamente relacionado con Churn Category. |

## ¿Por qué hemos escogido este dataset?

1. Es un caso de negocio real y muy relevante: La predicción de churn (abandono de clientes) es uno de los problemas más importantes en este tipo de empresas.

2. Perfecto para la aplicación de algoritmos de Machine Learning:
    - Análisis exploratorio de los datos.
    - Limpieza y preprocesamiento.
    - Modelos de clasificación.
    - Evaluación de modelos.

3. Mezcla interesante de variables categóricas y numéricas, bueno para prácticar transformaciones de columnas como normalizado o label encoding.

4. Desbalanceo moderado (aproximadamente un 26.5% churn), ideal para probar técnicas de manejo de clases desbalanceadas.

5. Tamaño manejable, pero suficientemente grande para obtener buenos resultados significativos sin necesidad de infraestructura pesada.


## ¿Qué problema de negocio resolvemos? 

La compañía de telecomunicaciones pierde dinero cada vez que un cliente se da de baja. El objetivo del proyecto es predecir con la mayor antelación posible qué clientes tienen alta probabilidad de abandonar el servicio ('Churn' = Yes, o 'Churn Label' = 1), encontrar el porqué de dicho abandono y además determinar que características comunes tienen los perfiles que abandonan para proponer soluciones y así "redirigir" ese abandono con medidas de negocio. Al solucionar dicho problema, permitimos la posibilidad de actuar preventivamente con campañas de retención (descuentos, mejoras de servicio, llamadas proactivas...).

Por lo tanto, con un buen modelo podemos:

- Reducir la tasa de churn.
- Priorizar recursos, ofreciendo descuentos a los clientes con mayor riesgo de abandonar la empresa.
- Reducir el número de clientes con alto CLTV (Customer Lifetime Value) que abandonan la compañía.


## Planteamiento del problema en términos científicos

El proyecto busca abordar el problema de la predicción de la deserción de clientes utilizando datos históricos para inferir la probabilidad de que un cliente abandone la compañía en el futuro cercano. Esto se puede utilizar para predecir de manera anticipada si a medida que pasa el tiempo un cliente dado abandonará la compañía o no.

1. Tipo de Aprendizaje

Se utilizará aprendizaje supervisado, específicamente algoritmos de clasificación como regresión logística, Naive Bayes y Árboles de decisión entre los que se comparará la calidad de predicción para determinar la mejor forma de predecir el abandono.

2. Definición del Target y los Vectores de Atributos

La variable objetivo a predecir es la columna "Churn Label". Mientras que los vectores de atributos que utilizarán los modelos serán "Gender", "Senior Citizen", "Partner","Dependents", "Tenure Months","Phone Service", "Multiple Lines","Internet Service", "Online Security","Online Backup", "Device Protection""Tech Support", "Streaming TV","Streaming Movies", "Contract","Paperless Billing", "Payment Method","Monthly Charges", "Total Charges".


## Limitaciones

Para concluir la descripción del proyecto nos gustaría mencionar aspectos a considerar para que el que lo lea sea consciente de antemano tanto de las limitaciones del dataset como del porqué de las decisiones que hemos tomado:

Aunque hemos encontrado inconsistencias como datos que no corresponden, eliminación de columnas irrelevantes o valores en blanco que sustituir, la naturaleza sintética del dataset hace que, a nivel de limpieza, esté relativamente limpio en comparación con los datos brutos de una empresa real.

Por otro lado queremos destacar que más allá de las predicciones ha sido de gran ayuda entrenar un modelo de regresión logística para comprender y limpiar los datos, porque al principio nos daba muy mal resultado y nos ha hecho preguntarnos si realmente el dataset estaba tan limpio como pensábamos.
