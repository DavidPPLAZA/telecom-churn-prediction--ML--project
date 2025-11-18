# PRACTICA-APRENDIZAJE-AUTOM-TICO-DAVID-JORGE-

README - Análisis de Churn de Clientes de Telecomunicaciones


##      Origen del Dataset: 

El dataset utilizado es "Telco Customer Churn", disponible en Kaggle en el siguiente enlace:
https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset/data

Se trata de un conjunto de datos clásico y muy utilizado en la comunidad de Data Science, creado originalmente por IBM y posteriormente compartido en múltiples plataformas. El dataset 7043 registros de clientes de una compañía de telecomunicaciones ficticia (ubicada en California) con información detallada sobre demografía, servicios contratados, tipo de contrato, facturación y comportamiento de pago.

##      ¿Por qué hemos escogido este dataset?

1. Es un caso de negocio real y muy relevante: La predicción de churn (abandono de clientes) es uno de los problemas más importantes en este tipo de empresas.

2. Perfecto para la aplicación de algoritmos de Machine Learning:
    - Análisis exploratorio de los datos.
    - Limpieza y preprocesamiento.
    - Modelos de clasificación.
    - Evaluación de modelos.

3. Mezcla interesante de variables categóricas y numéricas, con valores disfrazados ("No internet service"), y valores nulos, lo que obliga a trabajar bien el preprocesamiento.

4. Desbalanceo moderado (aproximadamente un 26.5% churn), ideal para probar técnicas de manejo de clases desbalanceadas.

5. Tamaño manejable (7043 filas), pero suficientemente grande para obtener buenos resultados significativos sin necesidad de infraestructura pesada.


##      ¿Qué problema de negocio resolvemos? 

La compañía de telecomunicaciones pierde dinero cada vez que un cliente se da de baja. El objetivo del proyecto es predecir con la mayor antelación posible qué clientes tienen alta probabilidad de abandonar el servicio ('Churn' = Yes, o 'Churn Label' = 1). Al solucionar dicho problema, permitimos la posibilidad de actuar preventivamente con campañas de retención (descuentos, mejoras de servicio, llamadas proactivas...).

Por lo tanto, con un buen modelo podemos:

- Reducir la tasa de churn.
- Priorizar recursos, ofreciendo descuentos a los clientes con mayor riesgo de abandonar la empresa.
- Aumentar el CLTV (Customer Lifetime Value) al retener clientes valiosos.

NOTA: somos conscientes de que el dataset es sintético. Sin embargo, hemos escogido este dataset debido a que, como hemos mencionado previamente, tiene valores disfrazados, valores nulos, y por ello nace la necesidad de  trabajar rigurosamente en el análisis exploratorio y de hacer un buen preprocesamiento de los datos.
Además, este dataset ofrece la posibilidad de aplicarle algoritmos de Machine Learning supervisados y no supervisados, por lo que ofrece un amplio abanico de algoritmos que se le pueden aplicar. A su vez, ofrece un nivel de "suciedad" y particularidades que obliga a hacer un buen EDA y preprocesamiento. Por tanto, consideramos que es ideal para practicar el flujo completo de un proyecto real de principio a fin.

# En resumen: resolvemos el problema de "el cliente ya se fue" y ofrecemos la posibilidad de una estrategia proactiva y personalizada de retención.