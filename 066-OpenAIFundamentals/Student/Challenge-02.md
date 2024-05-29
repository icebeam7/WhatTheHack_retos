# Reto 02: Modelos y Capacidades de OpenAI

[< Reto Anterior ](./Challenge-01.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-03.md)

## Introducción

En este desafío, aprenderás sobre las diferentes capacidades de los modelos de OpenAI y cómo elegir el mejor modelo para tu caso de uso.

Compararás el modelo gpt3.5 con el modelo gpt4 en este desafío.

En un mundo donde la disponibilidad y el desarrollo de modelos están siempre cambiando, el modelo que comparamos puede cambiar con el tiempo. Sin embargo, te animamos a entender los conceptos generales y el material de este Desafío porque las técnicas de comparación utilizadas pueden ser aplicables a escenarios donde estás comparando Modelos de Lenguaje de Gran Escala. Para obtener más información sobre modelos legados y modelos adicionales, consulta la [documentación](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/legacy-models) y el [catálogo de modelos de Azure](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-use-foundation-models?view=azureml-api-2) para más detalles.

## Descripción
Despliegue de modelos para el desafío:
- Despliega los siguientes modelos en tu recurso de Azure OpenAI utilizando estos nombres:
  - `gpt-4`
  - `gpt-35-turbo`

- Añade las credenciales requeridas de los recursos de Azure en el archivo `.env`

Preguntas que deberías poder responder al final de este desafío:
- ¿Cuáles son las capacidades de cada modelo de Azure OpenAI?
- ¿Cómo seleccionar el modelo adecuado para tu aplicación?
- ¿Qué modelo elegirías para resumir prompts?
- ¿Qué modelo elegirías para generar nuevos nombres?
- ¿Cómo recuperar embeddings?

Ejecutarás el siguiente Jupyter Notebook para este reto:
- `CH-02-ModelComparison.ipynb`

El archivo se puede encontrar en tu Codespace bajo la carpeta `/notebooks`.


Regresa aquí después de completar todas las tareas en el Jupyter Notebook para validar que has cumplido con los criterios de éxito para este desafío.

Secciones en este Desafío:
1. Visión general sobre cómo encontrar el modelo adecuado
   - 1.1 Familias de Modelos
   - 1.2 Capacidades de los Modelos
   - 1.3 Detalles de Precios
   - 1.4 Cuotas y Límites
   - 1.5 Mejores Usos de los Modelos
   - 1.6 Mejores Prácticas para la Selección de Modelos
2. Implementación
   - 2.0 Funciones Auxiliares
   - 2.1 Resumir Texto
   - 2.2 Resumen para una audiencia específica
   - 2.3 Resumir Causa y Efecto
   - 2.4 Generar Apodos
   - 2.5 Embeddings

## Criterios de Éxito

Para completar este desafío con éxito, deberías ser capaz de:
- Demostrar un entendimiento de cada modelo y sus casos de uso adecuados
- Mostrar un entendimiento de las diferencias entre modelos
- Seleccionar el modelo más adecuado para aplicar en diferentes escenarios
- Ejecutar correctamente todas las celdas de código

## Recursos Adicionales

- [Overview of Azure OpenAI Models](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/models)
- [Azure OpenAI Pricing Page](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/)
- [Request for Quota Increase](https://customervoice.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR4xPXO648sJKt4GoXAed-0pURVJWRU4yRTMxRkszU0NXRFFTTEhaT1g1NyQlQCN0PWcu)
- [Customize Models](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/fine-tuning?pivots=programming-language-studio)
