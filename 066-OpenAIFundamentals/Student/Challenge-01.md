# Reto 01: Prompt Engineerin

[< Reto Anterior](./Challenge-00.md) -  **[Home](../README.md)** - [Siguiente reto >](./Challenge-02.md)

## Prerrequisitos

* Despliega tus propios modelos AOAI en el [portal AOAI](https://oai.azure.com/portal/).
* Actualiza el archivo `.env.sample` (y guárdalo como `.env`) según los nombres de tus modelos si aún no lo has hecho.

## Introducción

A medida que los Modelos de Lenguaje de Gran Escala (LLMs) ganan popularidad y uso en todo el mundo, la necesidad de gestionar y monitorear sus resultados se vuelve cada vez más importante. En este desafío, aprenderás a usar técnicas de 'prompt engineering' para generar los resultados deseados para los LLMs.

## Descripción
Despliegue de modelos para el desafío:
- Despliega los siguientes modelos en tu recurso de Azure OpenAI:
  - `gpt-4`
  - `gpt-35-turbo`

**NOTA:** Para las familias de modelos actualmente disponibles, por favor consulta este enlace para más información: [Modelos del Servicio Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models).

- Añade las credenciales requeridas de los recursos de Azure en el archivo ``.env``. Siéntete libre de hacer cualquier modificación necesaria y luego renombra el archivo `.env-sample` a `.env`.

Preguntas que deberías ser capaz de responder al final de este desafío:
- ¿Qué es el principio de la iteración en los prompts?
- ¿Qué hiperparámetros podrías ajustar para hacer que la respuesta sea más diversa en términos de lenguaje?
- ¿Qué técnica de 'prompt engineering' podrías usar para ayudar al modelo a completar tareas difíciles como problemas matemáticos?

Ejecutarás el siguiente cuaderno de Jupyter para completar las tareas de este desafío:
- `CH-01-PromptEngineering.ipynb`

El archivo se puede encontrar en tu Codespace bajo la carpeta `/notebooks`.

Secciones en este Desafío:
1. Experimentación con Parámetros
2. Ingeniería de Mensajes del Sistema
3. Principios de Prompting Iterativo:

   3.1 Escribe instrucciones claras y específicas
   
   3.2 Dale al modelo tiempo para "pensar"



## Recursos Adicionales
- [Introduction to prompt engineering](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/prompt-engineering)
- [Prompt engineering techniques](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/advanced-prompt-engineering?pivots=programming-language-chat-completions)
- [System message framework and template recommendations for Large Language Models (LLMs)](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/system-message)
- [Introduction to Azure OpenAI Service](https://learn.microsoft.com/en-us/training/modules/explore-azure-openai/)
- [Learn how to prepare your dataset for fine-tuning](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/prepare-dataset)
- [Learn how to customize a model for your application](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/fine-tuning?pivots=programming-language-studio)
