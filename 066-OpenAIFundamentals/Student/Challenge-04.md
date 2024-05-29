# Reto 04: Generación Aumentada por Recuperación (RAG) 

[< Reto Anterior](./Challenge-03.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-05.md)

## Prerrequisitos

- Recurso de Azure Form Recognizer para extraer texto de datos no estructurados en bruto.
- Recurso de Azure Cognitive Search para la indexación y recuperación de información relevante.
- Servicio de Azure OpenAI para modelos de IA generativos y modelos de incrustación.
- Añade las credenciales necesarias de los recursos anteriores en el archivo `.env`.

## Introducción

Las bases de conocimiento son ampliamente utilizadas en las empresas y pueden contener un número extenso de documentos en diversas categorías. Recuperar contenido relevante basado en consultas de usuarios es una tarea desafiante. Tradicionalmente, métodos como Page Rank han sido empleados para recuperar información de manera precisa a nivel de documento. Sin embargo, los usuarios aún necesitan buscar manualmente dentro del documento para encontrar la información específica y relevante que necesitan. Los recientes avances en Modelos de Base, como los desarrollados por OpenAI, ofrecen una solución a través del uso de técnicas de "Generación Aumentada por Recuperación" y codificación de información como "Incrustaciones". Estos métodos ayudan a encontrar la información relevante y luego responder o resumir el contenido para presentarlo al usuario de manera concisa y sucinta.

La generación aumentada por recuperación (RAG, por sus siglas en inglés) es un enfoque innovador que combina el poder de las bases de conocimiento basadas en recuperación, como Azure Cognitive Search, y modelos de lenguaje de gran tamaño (LLMs), como Azure OpenAI ChatGPT, para mejorar la calidad y relevancia de los resultados generados. Esta técnica implica integrar un componente de recuperación en un modelo generativo, permitiendo la recuperación de información contextual y específica del dominio desde la base de conocimiento. Al incorporar este conocimiento contextual junto con la entrada original, el modelo puede generar resultados deseados, como resúmenes, extracción de información o respuesta a preguntas. En esencia, la utilización de RAG con LLMs te permite generar salidas de texto específicas del dominio incorporando datos externos específicos como parte del contexto proporcionado a los LLMs.

RAG busca superar las limitaciones encontradas en modelos puramente generativos, incluyendo problemas de precisión factual, relevancia y coherencia, a menudo vistos en forma de "alucinaciones". Al integrar la recuperación en el proceso generativo, RAG busca mitigar estos desafíos. La incorporación de información recuperada sirve para "anclar" los modelos de lenguaje de gran tamaño (LLMs), asegurando que el contenido generado se alinee mejor con el contexto previsto, mejore la corrección factual y produzca resultados más coherentes y significativos.

## Descripción

Preguntas que deberías poder responder al final del reto:

- ¿Cómo creamos experiencias similares a ChatGPT con datos empresariales? En otras palabras, ¿cómo "anclamos" Modelos de Lenguaje de Gran Tamaño (LLMs) principalmente a nuestros propios datos?
- ¿Por qué es tan importante la combinación de los pasos de recuperación y generación y cómo permiten la integración de bases de conocimiento y LLMs para tareas de IA descendentes?
- Dadas las limitaciones del límite de tokens, ¿cómo ayuda el enfoque RAG a manejar documentos largos y complejos?
- ¿Cómo se puede aplicar este enfoque a una amplia gama de aplicaciones como respuesta a preguntas, resumen, sistemas de diálogo y generación de contenido?

Algunas consideraciones:

- **Desafíos de evaluación:** Evaluar el rendimiento de RAG presenta desafíos, ya que las métricas tradicionales pueden no capturar completamente las mejoras logradas a través de la recuperación. Desarrollar métricas de evaluación específicas para la tarea o realizar evaluaciones humanas puede proporcionar evaluaciones más precisas de la calidad y efectividad del enfoque.
- **Consideraciones éticas:** Aunque RAG proporciona capacidades poderosas, también introduce consideraciones éticas. El componente de recuperación debe ser cuidadosamente diseñado y evaluado para evitar la recuperación de información sesgada o dañina. Además, el contenido generado debe ser monitoreado y controlado para asegurar que se alinee con las pautas éticas y no propague desinformación o sesgos dañinos.

Ejecutarás los siguientes dos Jupyter Notebook para este desafío:

- `CH-04-A-RAG_for_structured_data.ipynb`
- `CH-04-B-RAG_for_unstructured_data.ipynb`

Estos archivos se pueden encontrar en tu Codespace bajo la carpeta `/notebooks`.

Regresa aquí a la guía del estudiante después de completar todas las tareas en el cuaderno de Jupyter para validar que has cumplido con los criterios de éxito para este desafío.

## Criterios de éxito


Para completar este desafío con éxito, deberías ser capaz de:
- Verificar que has extraído texto de datos no estructurados usando la API de Azure Document Intelligence en un formato más estructurado como JSON.
- Verificar que has creado un índice usando Azure Cognitive Search basado en el tipo de datos con los que estás trabajando y cargar datos en el índice.
- Demostrar el uso del Desarrollo de Prompts Iterativos para escribir prompts efectivos para tus tareas de IA.

## Recursos de Aprendizaje

- [Usar OpenAI GPT con tus Datos Empresariales](https://techcommunity.microsoft.com/t5/startups-at-microsoft/use-openai-gpt-with-your-enterprise-data/ba-p/3817141)
- [ChatGPT + Datos Empresariales con Azure OpenAI y Cognitive Search](https://github.com/Azure-Samples/azure-search-openai-demo)
- [Construir LLMs Específicos de la Industria Usando Generación Aumentada por Recuperación](https://towardsdatascience.com/build-industry-specific-llms-using-retrieval-augmented-generation-af9e98bb6f68)

## Desafíos Avanzados (Opcional)

¿Te sientes demasiado cómodo? ¿Ansioso por hacer más? ¡Intenta estos desafíos adicionales!

- Piensa en cómo puedes evaluar tus respuestas y el rendimiento de RAG. ¿Qué técnicas puedes aplicar?
- Piensa en cómo puedes moderar preguntas dañinas de los usuarios, evitar sesgos y mitigar ataques de inyección de prompts.
