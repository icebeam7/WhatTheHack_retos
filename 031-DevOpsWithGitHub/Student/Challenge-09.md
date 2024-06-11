# Desafío 09 - Ramas y Políticas

[<  Reto Anterior](Challenge-08.md) - [Home](../README.md) - [Siguiente reto >](Challenge-10.md)

## Introducción

¡En los pasos anteriores, implementamos con éxito una canalización CI/CD de extremo a extremo! Sin embargo, nuestro flujo de trabajo actual promoverá inmediatamente cada pequeño cambio directamente a producción. Normalmente, querrás evitar trabajar directamente en la rama principal de tu repositorio para evitar conflictos y proteger el entorno de producción.

Con GitHub, podemos resolver estos desafíos utilizando una práctica llamada ramificación. Algunos pueden referirse a esto como el [flujo de GitHub](https://guides.github.com/introduction/flow/). Cuando un desarrollador quiere hacer un cambio, agregar una característica o corregir un error, comienza creando una nueva 'rama' o copia de la base de código principal. Luego, el desarrollador realiza cambios y los confirma. Crea una solicitud de extracción para fusionar estos cambios de nuevo en la rama principal. Esta solicitud de extracción puede o no involucrar algunas pruebas o discusiones. Finalmente, los cambios se fusionan de nuevo en la base de código principal y la rama se puede eliminar.

En este desafío, practicarás este flujo. Además, GitHub ofrece una característica para proteger explícitamente contra cambios directos a la rama principal. Estas se llaman reglas de protección de ramas y comenzarás implementando una.

## Descripción

- Crea una regla de protección de ramas que evite que los desarrolladores comprometan cambios en la rama principal del repositorio.

- Crea una rama de características, realiza un pequeño cambio en el código (por ejemplo, `/Application/aspnet-core-dotnet-core/Views/Home/Index.cshtml`), y sincroniza esta rama con el repositorio de GitHub.

- Define un propietario de código para el directorio `/Application`. Tu política de ramas debe requerir una revisión del propietario del código.

- Crea y completa una Solicitud de Extracción, fusionando tu cambio de código en la rama protegida.

## Criterios de Éxito

- Tienes una regla de protección de ramas que impide cambios en la rama principal.

- Los cambios en la aplicación (por ejemplo, `/Application/aspnet-core-dotnet-core/Views/Home/Index.cshtml`) se confirman en una rama de características.

- Antes de completar una solicitud de extracción:
    - Un propietario de código debe aprobar los cambios ([consejo](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/about-code-owners))
    - Un flujo de trabajo CI se ejecuta contra la rama de características asegurando que la aplicación pase una construcción y prueba ([consejo](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/enabling-required-status-checks))

- Una solicitud de extracción completada se fusiona con la rama protegida y se despliega automáticamente en el entorno de desarrollo.


## Recursos de Aprendizaje

- La información general sobre ramas protegidas se puede encontrar [aquí](https://docs.github.com/en/github/administering-a-repository/about-protected-branches), con más detalles de configuración [aquí](https://docs.github.com/en/github/administering-a-repository/configuring-protected-branches).
- La información general sobre ramas se puede encontrar [aquí](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-branches), con más detalles sobre creación y eliminación [aquí](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository).
- La información general sobre pull requests se puede encontrar [aquí](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests), con más detalles sobre [creación](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) y [revisión](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests).
- [Sobre propietarios de código](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/about-code-owners)
- [Habilitar verificaciones de estado requeridas](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/enabling-required-status-checks)
- [Sobre revisiones requeridas para solicitudes de extracción](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/about-required-reviews-for-pull-requests)

## Consejos

- Si tu cuenta de GitHub se creó en el nivel 'Gratis', para crear una regla de Protección de Ramas tu repositorio debe ser público. Para cambiar un repositorio de privado a público, visita la pestaña 'Configuración' y desplázate hasta la parte inferior donde tienes la opción de 'Cambiar visibilidad'.
- Si usas la interfaz de línea de comandos de git, puedes encontrar una serie de comandos de git útiles para ramificación [aquí](https://gist.github.com/JamesMGreene/cdd0ac49f90c987e45ac). (Asegúrate de enfocarte en los comandos 'git', en lugar de 'gitflow').
- Si usas la interfaz de línea de comandos de git, intenta agregar '--help' después de un comando para obtener información útil sobre argumentos y uso.

## Desafíos Avanzados (opcionales)

En este desafío, nos enfocamos en crear una rama de características directamente desde la rama principal. Sin embargo, algunas organizaciones prefieren hacer implementaciones por fases. En lugar de fusionar ramas de características directamente en producción, esta estrategia alternativa implica tener una rama de producción principal y una rama de desarrollo que se ejecuta en paralelo a la rama principal. Las ramas de características y corrección de errores se crean a partir de y se fusionan en la rama de desarrollo. Cuando quieras lanzar nuevas características a producción, crea una solicitud de extracción para fusionar los cambios de desarrollo en la rama principal.

Si deseas explorar este flujo, intenta configurar tu repositorio para estas 'implementaciones por fases.' Comienza creando una rama de desarrollo a partir de tu rama principal. En la rama de desarrollo, repite el flujo anterior. Cuando estés listo para lanzar, crea y completa una solicitud de extracción fusionando la rama de desarrollo en la rama principal.

**IMPORTANTE**: No elimines la rama de desarrollo después de completar la implementación. Querrás usar esta misma rama para repetir el proceso para tu próxima implementación.

[<  Reto Anterior](Challenge-08.md) - [Home](../README.md) - [Siguiente reto >](Challenge-10.md)

