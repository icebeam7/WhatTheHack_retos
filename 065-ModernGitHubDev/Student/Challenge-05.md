# Reto 05 - Despliegue del proyecto

[< Reto Anterior ](./Challenge-04.md) - **[Home](../README.md)**

## Introducción

El refugio está bastante satisfecho. Has actualizado la aplicación con una nueva característica, configurado controles de seguridad y creado un entorno en Azure para alojar el proyecto. ¡Ha llegado el momento de desplegar el proyecto!

Dado que la aplicación continuará creciendo con nuevas características en un futuro cercano, el refugio desea asegurar que el proceso de despliegue sea eficiente. Siempre que se envíe nuevo código a `main`, este debería ser desplegado en producción.

## Descripción

Completarás este hack creando una última [GitHub Action](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions) para desplegar el proyecto en Azure. Desplegar un proyecto puede ser bastante complejo dependiendo de los servicios utilizados y del [acuerdo de nivel de servicio (SLA)](https://es.wikipedia.org/wiki/Acuerdo_de_nivel_de_servicio) que se necesita cumplir. Por ejemplo, es posible que necesites configurar un [despliegue azul/verde](https://martinfowler.com/bliki/BlueGreenDeployment.html) para asegurar que no haya tiempo de inactividad cuando se publiquen nuevas características. Puedes hablar sobre diferentes escenarios con los mentores coach.

Para los propósitos de este hack, desplegarás en el [entorno que creaste anteriormente](./Challenge-04.md) cuando el código se envíe a `main`.

## Criterios de Éxito

- Demuestra que se ha creado un GitHub Action que despliega el sitio web en [Azure Container Apps](https://learn.microsoft.com/es-es/azure/container-apps/overview) cuando el código se envía a `main`.
- Verifica que la PR que creaste anteriormente se haya enviado a `main`.
- Demuestra que el sitio público muestra la aplicación del refugio, incluyendo la información de horarios del [componente que creaste anteriormente](./Challenge-01.md).


## Learning Resources

- [Entender las GitHub Actions](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions)
- [Activar un flujo de trabajo](https://docs.github.com/es/actions/using-workflows/triggering-a-workflow)
- [Implementación en Azure Container Apps con Acciones de GitHub](https://learn.microsoft.com/es-es/azure/container-apps/github-actions)
- [Azure Container Apps Build and Deploy - GitHub Actions](https://github.com/marketplace/actions/azure-container-apps-build-and-deploy)
- [GitHub Actions contexts](https://docs.github.com/es/actions/learn-github-actions/contexts)
- [Uso de secretos en GitHub actions](https://docs.github.com/es/actions/security-guides/using-secrets-in-github-actions)

## Tips

- Puedes concatenar cadenas al definir un workflow usando secretos o variables y literales de cadena.
- El nombre del 'Azure Container Registry' será **`<your_prefix>`acr**
- El nombre de la 'Azure Container App' será **`<your_prefix>`containerapp**
- El nombre de la ' Azure Container App' será **`<your_prefix>`containerappenvironment**
