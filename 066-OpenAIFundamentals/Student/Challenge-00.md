# Reto 00 - Prerrequisitos - En sus marcas, listos… ¡fuera!

**[Home](../README.md)** - [Siguiente reto >>](./Challenge-01.md)

## Introducción

Gracias por participar en el What The Hack Azure OpenAI Fundamentals. Antes de que puedas comenzar a hackear, necesitarás configurar algunos prerrequisitos.

## Descripción
En este desafío, configurarás los prerrequisitos necesarios y el entorno para completar el resto del hack, incluyendo:

- Acceder a Azure OpenAI
- GitHub Codespaces
- Configurar Azure OpenAI

### Acceso a Azure OpenAI

Para facilitar tu participación en el hackathon, te proporcionaremos las credenciales de una cuenta de Azure ya configurada con acceso a Azure OpenAI. Al inicio del desafío, recibirás instrucciones detalladas sobre cómo acceder a estas credenciales. Si en algún momento necesitas ayuda para acceder a los recursos, por favor, indícanoslo para asistirte de inmediato.

### GitHub Codespaces

Para facilitar el desarrollo y evitar complicaciones con dependencias, utilizaremos **GitHub Codespaces**. Este es un entorno de desarrollo alojado en la nube, accesible desde tu navegador, que simplifica considerablemente la configuración inicial.

Cada cuenta personal de GitHub incluye un plan gratuito que ofrece aproximadamente 120 horas al mes para operar Codespaces, lo que te permite trabajar sin preocuparte por la configuración local de tu equipo. Puedes revisar el saldo de tus horas disponibles en la [página de facturación de GitHub](https://github.com/settings/billing/summary).

Para comenzar, sigue estos pasos:

1. Accede al [repositorio de Codespace](https://github.com/WhatTheHack-CF/wth-openaifundamentals) que usaremos para el hack.
2. Inicia sesión con tu cuenta personal de GitHub, no uses una cuenta gestionada por tu empresa.
3. Verás que el repositorio es una plantilla. Utiliza esta plantilla para crear un repositorio en tu cuenta personal.
4. Dentro de tu nuevo repositorio, crea un Codespace seleccionando la opción "Codespaces" y luego "Crear codespace en main".

Este entorno ya tiene preinstaladas todas las herramientas necesarias, permitiéndote concentrarte completamente en el desarrollo.

### Configuración de Azure OpenAI

Una vez que hayas configurado tu  Jupyter Notebook, crea un recurso de Azure OpenAI en tu suscripción de Azure y realiza algunas configuraciones iniciales.

- [Crear un Recurso de Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource?pivots=web-portal)
- Despliega los siguientes modelos en tu recurso de Azure OpenAI:
  - `gpt-4`
  - `gpt-35-turbo`
  - `text-embedding-ada-002`

#### Configuración del Archivo de Jupyter Notebooks

El código en un  Jupyter Notebooks obtiene sus valores de configuración de variables de entorno configuradas en un archivo `.env`. Algunos de estos valores de configuración son secretos (como la clave para acceder a tu recurso de Azure OpenAI).

**NOTA:** Un archivo `.env` nunca debe almacenarse en un repositorio de Git. Por lo tanto, hemos proporcionado un archivo de muestra llamado `.env.sample` que contiene una lista de las variables de entorno requeridas por el Jupyter Notebook.

Encontrarás el archivo `.env.sample` en la raíz del codespace. 

- Renombra el archivo de `.env.sample` a `.env`.
- Añade las credenciales requeridas de los recursos de Azure en el archivo `.env`.

  **SUGERENCIA:** Puedes obtener estas credenciales a través del Portal de Azure dentro de tu recurso AOAI. Haz clic en `Keys and Endpoint` desde el menú desplegable en el lado izquierdo.

  **CONSEJO:** Aprende más sobre el uso de archivos `.env` [aquí](https://dev.to/edgar_montano/how-to-setup-env-in-python-4a83#:~:text=How%20to%20setup%20a%20.env%20file%201%201.To,file%20using%20the%20following%20format%3A%20...%20More%20items).
  
**NOTA:** Recursos adicionales de Azure como Azure Form Recognizer (también conocido como Azure Document Intelligence) y Azure Cognitive Search (también conocido como Azure AI Search) serán necesarios para desafíos posteriores. Puedes añadir estos valores al archivo `.env` más adelante a medida que avances en los desafíos.

**NOTA:** También hemos proporcionado un archivo `.gitignore` que debería evitar que accidentalmente hagas un commit de tu archivo `.env` renombrado a un repositorio de Git durante este hack.


## Criterios de Éxito

Para completar este desafío con éxito, deberías poder:

- Verificar que tienes los siguientes archivos y carpetas disponibles en el Codespace:
    - `/data`
    - `/notebooks`
    - `.env` <= Renombrado de `.env.sample`
    - `.gitignore`
    - `requirements.txt`
- Verificar que has creado el recurso de Azure OpenAI y desplegado los modelos necesarios en tu suscripción de Azure.

## Recursos de Aprendizaje

- [GitHub Codespaces Overview](https://docs.github.com/en/codespaces/overview)
- [Jupyter Notebooks in VS Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- [Jupyter Notebooks](https://jupyter.org/)
- [Project Jupyter](https://en.wikipedia.org/wiki/Project_Jupyter)
- [How to setup .env in Python](https://dev.to/edgar_montano/how-to-setup-env-in-python-4a83#:~:text=How%20to%20setup%20a%20.env%20file%201%201.To,file%20using%20the%20following%20format%3A%20...%20More%20items)
