# Challenge 03 - Grounding, Chunking, and Embedding

[< Reto Anterior](./Challenge-02.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-04.md)


## Prerrequisitos

* Recurso de Azure Cognitive Search para la indexación y recuperación de información relevante.
* Servicio de Azure OpenAI para modelos de IA generativos y modelos de incrustación.
* Añade las credenciales necesarias de los recursos anteriores en el archivo `.env`.

## Introducción

Al trabajar con modelos de lenguaje de gran tamaño (LLM), es importante entender cómo anclarlos con los datos correctos. Además, examinarás cómo manejar los límites de tokens cuando tienes muchos datos. Finalmente, experimentarás con incrustaciones. Este desafío te enseñará todos los conceptos fundamentales - Anclaje, Segmentación, Incrustación - antes de verlos en acción en el Desafío 4. A continuación, se presentan breves introducciones a los conceptos que aprenderás.

El anclaje es una técnica utilizada cuando quieres que el modelo devuelva respuestas confiables a una pregunta dada.
La segmentación es el proceso de desglosar un documento grande. Ayuda a limitar la cantidad de información que pasamos al modelo.
Una incrustación es una representación densa en información del significado semántico de un texto.

## Descripción

Preguntas que deberías poder responder al final del desafío:

- ¿Por qué es importante el anclaje y cómo puedes anclar un modelo LLM?
- ¿Qué es un límite de tokens?
- ¿Cómo puedes manejar los límites de tokens? ¿Cuáles son las técnicas de segmentación?
- ¿Qué logran las incrustaciones?

Ejecutarás los siguientes tres cuadernos de Jupyter para este desafío:

* `CH-03-A-Grounding.ipynb`
* `CH-03-B-Chunking.ipynb`
* `CH-03-C-Embeddings.ipynb`

Estos archivos se pueden encontrar en tu Codespace bajo la carpeta `/notebooks`.


## Criterios de Éxito

Para completar este desafío con éxito, deberías ser capaz de:
- Verificar que puedes anclar un modelo a través del mensaje del sistema
- Demostrar diversas técnicas de segmentación
- Demostrar cómo crear incrustaciones

## Recursos Adicionales

* [Grounding LLMs](https://techcommunity.microsoft.com/t5/fasttrack-for-azure/grounding-llms/ba-p/3843857)
* [Embeddings example](https://github.com/openai/openai-cookbook/blob/main/examples/Embedding_Wikipedia_articles_for_search.ipynb)
* [Langchain Chunking](https://js.langchain.com/docs/modules/indexes/text_splitters/examples/recursive_character)
  
