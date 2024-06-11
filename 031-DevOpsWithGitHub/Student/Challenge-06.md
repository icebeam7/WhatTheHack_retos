
# Reto 06 - Integración Continua (CI)

[<  Reto Anterior](Challenge-05.md) - [Home](../README.md) - [Siguiente reto >](Challenge-07.md)

## Introducción

Con nuestros recursos de Azure creados, hemos establecido las bases para nuestra aplicación. Ahora, debemos conectar nuestro código fuente con su destino. El primer paso en este proceso se llama Integración Continua (CI).

La integración continua es el proceso de fusionar los cambios de código local en el control de versiones e incluye pasos para compilar y/o probar el código automáticamente. Cuando se hace de manera efectiva, la Integración Continua permite a los desarrolladores iterar y colaborar rápidamente, y ayuda a garantizar que el nuevo código agregado no rompa la aplicación actual.

Revisa los siguientes artículos:
- [Acerca de la integración continua](https://docs.github.com/en/actions/building-and-testing-code-with-continuous-integration/about-continuous-integration)
- [Configurar la integración continua usando plantillas de flujo de trabajo](https://docs.github.com/en/actions/building-and-testing-code-with-continuous-integration/setting-up-continuous-integration-using-github-actions)

## Descripción

En este reto, construirás y probarás la aplicación .NET Core.

- Crea un nuevo flujo de trabajo de `.NET`.

   **NOTA:** Para obtener un nuevo flujo de trabajo de ejemplo, en tu repositorio, haz clic en Acciones en el menú superior > Nuevo flujo de trabajo (botón) > desplázate hacia abajo hasta la sección 'Flujos de trabajo de integración continua' y selecciona el botón de configurar en el ejemplo de '.NET'.

- Revisa la estructura del flujo de trabajo. Hay un solo trabajo (llamado 'build') con múltiples pasos (restore, build, test).

   **NOTA:** Hay algunos eventos nuevos para el flujo de trabajo que no hemos usado antes, como 'push' y 'pull_request'.

- En tu flujo de trabajo, bajo el paso "Setup .NET Core", verifica que la versión de .NET sea `6.0.x` para coincidir con la versión definida por la aplicación.

- Asegúrate de que el flujo de trabajo esté configurado para desencadenarse tanto en pushes *como* en pull requests.

- Configura ambos desencadenadores con filtros de ruta para que *solo* se active este flujo de trabajo para cambios en la carpeta `/Application`.

- Actualiza los pasos predefinidos utilizados para construir la aplicación .NET Core.

   **NOTA:** Para cada paso a continuación, necesitarás actualizar cada comando para pasar la ruta relativa al archivo `.csproj` como argumento:
   - `restore` - obtendrá todas las dependencias. Actualiza con un [argumento](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-build#arguments) al archivo csproj de la aplicación.
   - `build` - compilará nuestro código. Actualiza con un argumento al archivo csproj de la aplicación.
   - `test` - ejecutará todas nuestras pruebas unitarias. Actualiza con un argumento al archivo csproj de pruebas unitarias.

- Prueba el flujo de trabajo haciendo un pequeño cambio en el código de la aplicación (por ejemplo, agrega un comentario). Haz commit, push y asegúrate de que el flujo de trabajo se complete con éxito.

En este punto, cualquier cambio empujado a la carpeta `/Application` activará automáticamente el flujo de trabajo... ¡y eso es Integración Continua!

## Criterios de éxito

- Cualquier cambio empujado a la carpeta `/Application` activará automáticamente el flujo de trabajo.
- Los pasos de restauración, compilación y prueba de .NET Core se completan con éxito.

## Recursos de aprendizaje

- [Introducción a GitHub Actions](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/introduction-to-github-actions)
- [Acción de .NET Core para construir y probar](https://github.com/actions/starter-workflows/blob/dacfd0a22a5a696b74a41f0b49c98ff41ef88427/ci/dotnet-core.yml)
- [Comprensión de los filtros de ruta del flujo de trabajo](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions#onpushpull_requestpaths)
- [Comandos dotnet](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet#dotnet-commands)
- [GitHub Actions para Azure](https://github.com/Azure/actions)

## Consejos

- Si tienes problemas para encontrar un punto de partida, intenta hacer clic en la pestaña 'Actions' de tu repositorio de GitHub.
- ¡Aprovecha las plantillas de flujo de trabajo preconstruidas que a menudo te ahorrarán mucho trabajo!

## Desafíos avanzados (opcionales)

- En este reto, si el flujo de trabajo falla, se envía un correo electrónico al propietario del repositorio. A veces, es posible que desees registrar o crear un issue en GitHub cuando el flujo de trabajo falla.
    - Agrega un paso a tu flujo de trabajo para crear un issue en GitHub cuando haya una falla.


[<  Reto Anterior](Challenge-05.md) - [Home](../README.md) - [Siguiente reto >](Challenge-07.md)

---

