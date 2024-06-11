# Reto 10 - Seguridad

[< Reto Anterior](Challenge-09.md) - [Home](../README.md) - [Siguiente reto >](Challenge-11.md)

## Introducción

¡Nuestra aplicación está funcionando! Incluso estamos usando un flujo de Git adecuado para protegernos contra cambios no deseados en nuestra rama principal y estamos registrando la telemetría de la aplicación en App Insights. Sin embargo, antes de estar verdaderamente listos para producción, hay un tema que debemos cubrir: la seguridad.

Una buena práctica de DevOps es habilitar protecciones contra vulnerabilidades a nivel de código, y GitHub proporciona varias características útiles en esta área. Primero, están los Issues, que permiten a los desarrolladores o usuarios abrir 'tickets' indicando errores a corregir o posibles vulnerabilidades. Si tu organización prefiere que las fallas de seguridad se informen en un lugar diferente a GitHub, tienes la opción de proporcionar una política de seguridad personalizada que describa el proceso de reporte.

Además de estos procesos manuales, GitHub también ofrece herramientas automatizadas para escanear el código en busca de errores comunes. En este desafío, utilizarás el Dependabot integrado, que proporciona alertas si tu repositorio contiene bibliotecas, paquetes o dependencias externas con vulnerabilidades conocidas. También configurarás un flujo de trabajo con CodeQL que puede escanear tu código fuente en busca de errores comunes de codificación o fallas básicas de seguridad.

## Descripción

En este desafío, mejorarás la seguridad de tu repositorio utilizando algunas de las herramientas integradas de GitHub.

- Encuentra la política de seguridad del repositorio. Si existe una política, realiza una edición y fusiona tu cambio de nuevo en la rama principal. De lo contrario, crea una política utilizando la plantilla proporcionada. Las políticas de seguridad de GitHub son documentos Markdown que indican la forma preferida de reportar vulnerabilidades de seguridad para el repositorio.

- Habilita las alertas de Dependabot para el repositorio. Dependabot es una herramienta automatizada que crea una solicitud de extracción cuando alguna dependencia en la base de código tiene una vulnerabilidad conocida.

- Finalmente, configura y ejecuta un flujo de trabajo de escaneo de código para el repositorio usando el 'Análisis de CodeQL' de GitHub. Este flujo de trabajo puede ejecutarse en cada solicitud de extracción o según un cronograma, y verifica tu código en busca de vulnerabilidades o errores comunes.

## Criterios de éxito

- En GitHub, deberías poder ver los pull requests 'cerrados' que creó o actualizó la política de seguridad (archivo SECURITY.md).
- Además, deberías poder ver un nuevo pull request 'abierto' creada por Dependabot solicitando una actualización de una dependencia.
- Finalmente, deberías poder ver los resultados del análisis de CodeQL en la pestaña de Seguridad.

## Recursos de aprendizaje

- Aprende más sobre cómo agregar una política de seguridad a tu repositorio [aquí](https://docs.github.com/en/github/managing-security-vulnerabilities/adding-a-security-policy-to-your-repository).
- Aprende más sobre Dependabot y dependencias vulnerables [aquí](https://docs.github.com/en/github/managing-security-vulnerabilities/managing-vulnerabilities-in-your-projects-dependencies).
- Aprende más sobre el escaneo automatizado de código y la comprensión de resultados [aquí](https://docs.github.com/en/github/finding-security-vulnerabilities-and-errors-in-your-code).

## Consejos

- Si estás atascado, revisa la pestaña 'Seguridad' de tu repositorio en GitHub.

[<  Reto Anterior](Challenge-09.md) - [Home](../README.md) - [Siguiente reto >](Challenge-11.md)