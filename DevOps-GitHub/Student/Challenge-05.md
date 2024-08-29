# Reto 05 - Despliegue del proyecto

[< Reto Anterior](./Challenge-04.md) - **[Home](../README.md)**

## Introducción

El refugio está bastante satisfecho. Has actualizado la aplicación con una nueva característica, configurado controles de seguridad y creado un entorno en Azure para alojar el proyecto. ¡Ha llegado el momento de desplegar el proyecto!

Dado que la aplicación continuará creciendo con nuevas características en un futuro cercano, el refugio desea asegurar que el proceso de despliegue sea eficiente. Siempre que se envíe nuevo código a `main`, este debería ser desplegado en producción.

## Descripción

Completarás este hack creando una última [GitHub Action](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions) para desplegar el proyecto en Azure. Desplegar un proyecto puede ser bastante complejo dependiendo de los servicios utilizados y del [acuerdo de nivel de servicio (SLA)](https://es.wikipedia.org/wiki/Acuerdo_de_nivel_de_servicio) que se necesita cumplir. Por ejemplo, es posible que necesites configurar un [despliegue azul/verde](https://martinfowler.com/bliki/BlueGreenDeployment.html) para asegurar que no haya tiempo de inactividad cuando se publiquen nuevas características. Puedes hablar sobre diferentes escenarios con los mentores coach.

Para los propósitos de este hack, desplegarás en el [entorno que creaste anteriormente](./Challenge-04.md) cuando el código se envíe (push) a `main`.

> **Nota:** En el archivo Bicep, hay que hacer un cambio que está comentado. Búscalo, haz el cambio y asegurando que estés en la rama `main`. **IMPORTANTE: Para que el cambio surja efecto, debes ejecutar manualmente de nuevo el workflow del reto anterior** antes de hacer este despliegue. 

> Si te sientes abrumado con la action a crear, aquí puedes encontrar un [ejemplo de la acción a crear](https://gist.github.com/luislogosmx/384f7387d5a1e45dbe602265b2d023b8). Te pedimos que intentes hacerlo por ti mismo antes de utilizar el ejemplo.

En resumen, estos son los 2 pasos que hay que realizar:

- En la rama `main`, modifica el workflow que creaste en el reto anterior estableciendo el puerto que debes usar. Sincroniza los cambios con tu repositorio y vuelve a ejecutar el workflow desde la pestaña Actions. Tu url no funcionará, no te preocupes, eso se arregla después del siguiente paso.

- En la rama `main`, crea un nuevo workflow (el link al código está arriba) para desplegar la aplicación en Azure utilizando los recursos que ya generaste en el reto anterior. Cuando sincronices los cambios haciendo un push, este workflow se ejecutará automáticamente. Revisa el progreso en la pestaña Actions. Una vez concluido con éxito, revisa la url y deberá verse desplegada la página del refugio (intenta desde una ventana de incógnito para evitar que la caché te muestre la versión anterior).

## Criterios de Éxito

- Demuestra que se ha creado un GitHub Action que despliega el sitio web en [Azure Container Apps](https://learn.microsoft.com/es-es/azure/container-apps/overview) cuando el código se envía a `main`.
- Verifica que la PR que creaste anteriormente se haya enviado a `main`.
- Demuestra que el sitio público muestra la aplicación del refugio, incluyendo la información de horarios del [componente que creaste anteriormente](./Challenge-02.md).

## Recursos de Aprendizaje

- [Entender las GitHub Actions](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions)
- [Activar un flujo de trabajo](https://docs.github.com/es/actions/using-workflows/triggering-a-workflow)
- [Implementación en Azure Container Apps con Acciones de GitHub](https://learn.microsoft.com/es-es/azure/container-apps/github-actions)
- [Azure Container Apps Build and Deploy - GitHub Actions](https://github.com/marketplace/actions/azure-container-apps-build-and-deploy)
- [Contextos de GitHub Actions](https://docs.github.com/es/actions/learn-github-actions/contexts)
- [Uso de secretos en GitHub Actions](https://docs.github.com/es/actions/security-guides/using-secrets-in-github-actions)

## Tips

- El nombre del 'Azure Container Registry' será **`<your_prefix>`acr**
- El nombre de la 'Azure Container App' será **`<your_prefix>`containerapp**
- El nombre de la 'Azure Container App' será **`<your_prefix>`containerappenvironment**
- **`<your_prefix>`** se refiere a la variable **AZURE_PREFIX** creada en el reto anterior.
- Puedes concatenar cadenas al definir un workflow usando secretos o variables y literales de cadena.

## Resumen y próximos pasos

¡Felicitaciones! Has explorado los componentes principales de DevOps y cómo GitHub puede respaldar un ciclo de vida de desarrollo común. Comenzaste creando un repositorio y luego habilitando las configuraciones para proteger tu código. Creaste un entorno en el cual codificar y habilitaste la integración continua. Modificaste el código y exploraste el flujo de GitHub. Y, por último, implementaste tu aplicación en la nube. Con estas habilidades, puedes seguir desarrollando y aumentando tu conocimiento de DevOps.

> **IMPORTANTE:**: Recuerda tomar una captura de pantalla de tu aplicación ejecutándose en Azure. Debe mostrar la URL así como una mascota con tu nombre completo. Una vez que ya no vayas a usar los recursos implementados en Azure, puedes eliminarlos ejecutando el siguiente comando en la Terminal de tu GitHub Codespace:
> 
> `az group delete -n pets-workshop --yes`
> 
> La eliminación de recursos puede demorar varios minutos.

[< Reto Anterior](./Challenge-04.md) - **[Home](../README.md)**
