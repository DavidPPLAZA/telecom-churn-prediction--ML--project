# PRACTICA-APRENDIZAJE-AUTOM-TICO-DAVID-JORGE-

README - Análisis de Churn de Clientes de Telecomunicaciones

# Alumnos: 
s
-   Jorge Amat
-   David Plaza

Enlace del repositorio: https://github.com/David-Plaza/PRACTICA-APRENDIZAJE-AUTOM-TICO-DAVID-JORGE-.git

## Origen del Dataset: 

El dataset utilizado es **“Telco Customer Churn”**, disponible en Kaggle en el siguiente enlace:
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

### Posibles algoritmos para predecir el churn

- **Regresión logística**  
  Punto de partida básico. Es rápida de entrenar y relativamente fácil de interpretar, por lo que nos sirve como modelo de referencia para comparar el resto.

- **Naive Bayes**  
  Puede ser adecuado cuando trabajamos con muchas variables categóricas. Nos permite obtener una primera aproximación rápida al problema.

- **Árboles de decisión**  
  Pueden ayudar a entender qué factores están más relacionados con el abandono.

- **K-Means (análisis exploratorio)**  
  Es candidato a utilizarse de forma exploratoria para agrupar clientes con características similares y detectar perfiles de riesgo de churn que puedan no ser evidentes a simple vista.

### Definición del Target y los Vectores de Atributos

La variable objetivo a predecir es la columna "Churn Label". 
Mientras que los vectores de atributos que utilizarán los modelos serán "Gender", "Senior Citizen", "Partner","Dependents", "Tenure Months","Phone Service", "Multiple Lines","Internet Service", "Online Security","Online Backup", "Device Protection""Tech Support", "Streaming TV","Streaming Movies", "Contract","Paperless Billing", "Payment Method","Monthly Charges", "Total Charges".

## **Metodología del proyecto** 

## Estructura del repositorio
- `00_EDA` → exploración y limpieza inicial  
- `01_FEATURE_ENGINEERING` → transformaciones y selección de variables  
- `02_BALANCEO` → técnicas de balanceo de clases  
- `03_MODELADO` → comparación de modelos y resultados  


### Fase 0 — Limpieza y EDA (00_EDA)
**Objetivo:** dejar los datos listos y entender lo básico antes de modelar.

El procedimiento es el siguiente:

- Separación de los datos en **train/test**.
- Limpieza de columnas que no aportaban al objetivo (IDs, geografía, variables derivadas del churn, etc.).
- Corrección de valores “raros” en **Total Charges** (en este dataset aparecen espacios en blanco en algunos casos).
- Revisión rápida de distribuciones y primeras relaciones con el churn (por ejemplo, antigüedad, tipo de contrato, servicios contratados).

**Resultado de esta fase:** un conjunto de datos limpio y coherente para el pipeline.

----------------------------------------------------------

### Fase 1 — Feature engineering (01_FEATURE_ENGINEERING)
**Objetivo:** transformar las columnas para que los modelos las entiendan y, si aporta, quedarnos con las variables más útiles.

El planteamiento fue el siguiente:
- Preparación de variables para modelos base:
  - Variables numéricas: escalado.
  - Variables categóricas: codificación.
- Prueba de **selección de características** con técnicas de reducción de dimensiones (búsqueda de un número razonable de variables que mantenga el rendimiento sin complicar el modelo).

**Resultado de esta fase:** una versión “lista para modelos” y una selección de variables razonable para comparar enfoques.

----------------------------------------------------------

### Fase 2 — Balanceo de clases (02_BALANCEO)
**Objetivo:** tratar el desbalanceo de los datos, ya que hay significativamente más valores de churn = 0 que churn = 1, y en estos casos, muchos modelos tienden a acertar a base de predecir casi siempre que el cliente se queda.

El planteamiento fue el siguiente:
- Entrenamos un **baseline** y evaluamos si el modelo estaba ignorando en exceso la clase minoritaria.
- Probamos técnicas de balanceo (en particular, **oversampling**), que después se integran de forma limpia en un pipeline.

**Resultado de esta fase:** un enfoque de balanceo integrado para mejorar la detección del churn.

----------------------------------------------------------

### Fase 3 — Modelado y evaluación (03_MODELADO)
**Objetivo:** entrenar y comparar modelos, priorizando una métrica útil para el negocio.

Modelos probados:
- Regresión logística.
- Naive Bayes Gaussiano.
- Random Forest.
- XGBoost.
- Red neuronal con Pytorch.

**Evaluación:**
- Reservamos un conjunto **test** totalmente separado para obtener un resultado final realista.
- En este problema decidimos maximizar el recall de churn porque el error más caro para el negocio suele ser el falso negativo, ya que un cliente que se iba y no es detectado, es perdido automáticamente sin que la empresa pueda reaccionar. En cambio, un falso positivo (pensar que alguien se va y luego no se va) normalmente solo implica el coste de una acción de retención (una llamada, una oferta o una revisión), que suele ser mucho menor que perder al cliente
- También decidimos analizar la precisión y el F1 score para asegurarnos de que el modelo no “dispara a todo” (recall alto pero con demasiadas falsas alarmas). La idea es lograr recall alto, pero manteniendo un equilibrio razonable para que las acciones de retención sean viables.

----------------------------------------------------------

## Resultados principales 

Tabla (métricas de la **clase churn = 1**):

| Modelo | Precision | Recall | F1 score |
|---|---:|---:|---:|
| Regresión logística | 0.52 | 0.80 | 0.63 |
| Naive Bayes Gaussiano | 0.52 | 0.79 | 0.63 |
| Random Forest | 0.54 | 0.80 | 0.64 |
| XGBoost | 0.52 | 0.83 | 0.64 |
| Red neuronal | 0.49 | 0.88 | 0.63 |

Lectura rápida:
- **XGBoost**: mejor equilibrio global (recall alto manteniendo una precisión razonable).
- **Regresión logística**: muy competitiva y además es fácil de explicar.
- **Red neuronal**: sube el recall, pero aumenta las falsas alarmas (precisión más baja).

----------------------------------------------------------

## Conclusiones e interpretación 
A grandes rasgos, el churn tiende a concentrarse en perfiles como:
- Clientes con **contrato mes a mes**.
- Menor **antigüedad** (tenure bajo).
- Ciertas combinaciones de servicios/soporte (cuando el cliente siente que no le compensa o tiene incidencias).
- Variables de facturación pueden influir, pero no explican todo por sí solas.
-En el análisis exploratorio con clustering (K-Means), pudimos observar que aparecen grupos de clientes con patrones claros (por ejemplo, distintos niveles de tenure, tipo de contrato y cargos mensuales). Esto ayuda a identificar perfiles de riesgo y a plantear acciones de retención más segmentadas (aunque no es el modelo final de predicción).

Esto sugiere acciones típicas de retención:
- Ofertas dirigidas a clientes **mes a mes** para migrar a contratos más largos.
- Programas de seguimiento en los primeros meses.
- Mejoras en soporte/seguridad/servicios para perfiles con señales de riesgo.
- Campañas específicas por segmentos (los clusters obtenidos): en lugar de una única acción para todos, adaptar el mensaje/oferta a cada perfil detectado.

------------------------------------------------------------------


## Limitaciones

Para concluir la descripción del proyecto nos gustaría mencionar aspectos a considerar para que el que lo lea sea consciente de antemano tanto de las limitaciones del dataset como del porqué de las decisiones que hemos tomado:

Aunque hemos encontrado inconsistencias como datos que no corresponden, eliminación de columnas irrelevantes o valores en blanco que sustituir, la naturaleza sintética del dataset hace que, a nivel de limpieza, esté relativamente limpio en comparación con los datos brutos de una empresa real.

Además, al tratarse de un dataset pensado para análisis, no recoge del todo situaciones habituales en un entorno real, como cambios en tarifas, campañas comerciales, incidencias técnicas, competencia o decisiones internas de la empresa que pueden afectar al churn. Por eso, aunque los modelos funcionen bien en este contexto, al llevarlos a producción sería necesario validar de nuevo el rendimiento con datos reales y, probablemente, reentrenar y ajustar el enfoque.

Por último, también existe una limitación práctica ligada a la evaluación. Al optimizar una métrica como el recall, esto puede aumentar los falsos positivos, es decir, señalar como churn = 1 a clientes que finalmente no se irán. En un caso real habría que equilibrar esto con los costes de las acciones de retención, definir un umbral de decisión alineado con el negocio y comprobar que la estrategia es sostenible en el tiempo.