# Reto 08 – Entrega Continua (CD)

[<  Reto Anterior](Challenge-07.md) - [Home](../README.md) - [Siguiente reto >](Challenge-09.md)

## Introducción

En DevOps, después de automatizar nuestro proceso de construcción, queremos automatizar nuestro proceso de lanzamiento, lo hacemos con una técnica llamada Entrega Continua (CD). Tómate un momento para revisar este breve artículo que explica por qué esto es importante.

- [¿Qué es la Entrega Continua?](https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-delivery)

## Descripción

En este desafío, usaremos GitHub Actions para desplegar nuestra imagen de contenedor en el entorno de desarrollo.


Extiende el flujo de trabajo que creaste en el Desafío #7 para:

- Configurar tu entorno `dev` para extraer la última imagen del contenedor desde ACR.
   - Inicia sesión en Azure usando tu principal service, si es necesario ([pista](https://docs.microsoft.com/en-us/azure/app-service/deploy-container-github-action?tabs=service-principal#tabpanel_CeZOj-G++Q-3_service-principal))
   - Usa la acción `Azure/webapps-deploy@v2` [acción](https://github.com/Azure/webapps-deploy) para actualizar la Aplicación Web y extraer la última imagen desde ACR. Parámetros clave a configurar:
      - `app-name` - el nombre de la instancia de la aplicación web a la que apuntar
      - `images` - la ruta a la imagen que enviaste a ACR

- Haz un pequeño cambio en tu aplicación (i.e.,`/Application/aspnet-core-dotnet-core/Views/Home/Index.cshtml`), haz commit, push, monitorea el flujo de trabajo y verifica si el cambio aparece en la instancia de desarrollo del sitio web.

- Configura tu flujo de trabajo para desplegar en tus entornos `test` y `prod` después de una aprobación manual para *cada* entorno.

## Criterios de éxito

1. Un pequeño cambio en `/Application/aspnet-core-dotnet-core/Views/Home/Index.cshtml` se muestra automáticamente en el sitio web que se ejecuta en el entorno `dev` (i.e., `<prefix>devops-dev`.azurewebsites.net).
2. Se requiere una aprobación manual para desplegar en los entornos `test` y `prod`.

## Recursos de aprendizaje

- [Desplegar un contenedor personalizado en App Service usando GitHub Actions](https://docs.microsoft.com/en-us/azure/app-service/deploy-container-github-action?tabs=service-principal#tabpanel_CeZOj-G++Q-3_service-principal)
- [Usar entornos para despliegue](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)

[<  Reto Anterior](Challenge-07.md) - [Home](../README.md) - [Siguiente reto >](Challenge-09.md)