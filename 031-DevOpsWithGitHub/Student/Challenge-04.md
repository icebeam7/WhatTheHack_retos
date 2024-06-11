# Reto 04 - Tu Primer Flujo de Trabajo con GitHub Actions


[<  Reto Anterior](Challenge-03.md) - [Home](../README.md) - [Siguiente reto >](Challenge-05.md)

## Introducción

La automatización es una parte fundamental de un proceso DevOps efectivo que incorpora elementos como CI/CD, pero también procesos como IssueOps. GitHub Actions proporciona una plataforma para que GitHub responda a varios desencadenantes de eventos para ejecutar flujos de trabajo.

Los flujos de trabajo se desglosan en trabajos que contienen los pasos de automatización para completar estos trabajos. Estos pasos pueden ser un simple comando de CLI o una pieza de automatización predefinida definida como una GitHub Action del extenso Marketplace de GitHub.

Los trabajos pueden ejecutarse en Linux, Mac o Windows en la nube en un runner alojado, o ejecutarse en tus propias máquinas a través de un runner autohospedado. Todos los desafíos de hoy utilizarán runners alojados, pero tus requisitos después de hoy pueden incluir la necesidad de auto-hospedaje o una combinación de ambos.

Los trabajos pueden ejecutarse secuencialmente o en paralelo. Los trabajos secuenciales proporcionan la capacidad de definir tus secuencias de flujo de trabajo, por ejemplo, la necesidad de compilar una aplicación, luego probarla y luego implementarla. Mientras que, los trabajos en paralelo permiten la capacidad de escalar secciones de tu flujo de trabajo. Por ejemplo, compilar tu aplicación en x64 al mismo tiempo que ARM o, probar tu aplicación en Chrome al mismo tiempo que en Firefox.

Los flujos de trabajo comunes se definen para procesos tipo CI/CD, pero la flexibilidad de las acciones de GitHub para responder a una amplia gama de eventos de GitHub permite muchas otras posibilidades, como la capacidad de ejecutar un flujo de trabajo basado en la creación de un issue en tu proyecto.

## Descripción

Este desafío nos llevará a usar GitHub Actions para escribir tu primer flujo de trabajo. Este flujo de trabajo comenzará con un solo trabajo desencadenado por un evento manual, ampliándose para tener un segundo trabajo y un desencadenante de evento adicional.

- Crea un flujo de trabajo de GitHub en un directorio `.github/workflows` (`first-workflow.yml`) que se ejecute manualmente (*no* desencadenado por un push o pull request).

- En el flujo de trabajo, agrega un primer trabajo llamado job1 con dos pasos dentro de él. Los pasos deben ser comandos simples de CLI para mostrar `echo`  step1 y step2 según corresponda.

- Desencadena el flujo de trabajo que creaste para ejecutarse desde GitHub. Revisa el archivo de registro del flujo de trabajo para ver que tu trabajo se ejecutó y emitió las declaraciones de eco como se esperaba.

- Agrega un segundo trabajo llamado job2 a tu archivo yaml de flujo de trabajo. En este trabajo, agrega un paso, pero haz que este paso llame a una GitHub Action desde el Marketplace de GitHub. Un ejemplo fácil y divertido aquí puede ser usar algo simple como 'Cowsays', que toma una entrada de una cadena que usa para emitir una vaca en arte ASCII en los registros del flujo de trabajo, sin embargo, siéntete libre de explorar el marketplace para cualquier acción que desees incorporar.

  **NOTA:** Cuando mires una Acción en el marketplace, nota en la sección de Enlaces a la derecha el enlace del repositorio a un repositorio público con el código que respalda esa acción.

- Ejecuta tu flujo de trabajo nuevamente asegurándote de que ambos trabajos se ejecuten como se esperaba.

  **NOTA:** Estos trabajos se han ejecutado en paralelo.

- Modifica tu archivo yaml de flujo de trabajo para que job2 se ejecute secuencialmente después de que job1 se complete. Ejecuta el flujo de trabajo nuevamente para probar la secuencia.

- Finalmente, modifica tu archivo yaml de flujo de trabajo con un desencadenante adicional que se active cuando se cree un issue.

## Criterios de Éxito

- Ser capaz de ejecutar tu primer flujo de trabajo desde un desencadenante manual o la creación de un issue.
- Ser capaz de ver la salida de todos los pasos en los dos trabajos.
- Los dos trabajos ahora se ejecutan secuencialmente con job2 ejecutándose después de que job1 se complete.
- job2 ejecuta con éxito una GitHub Action desde el marketplace.

## Recursos de Aprendizaje

- [Entender GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/understanding-github-actions)
- [Características esenciales de GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/essential-features-of-github-actions)
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
- [Desencadenar manualmente un flujo de trabajo](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch)
- [Eventos que desencadenan flujos de trabajo](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)
- [Variables de GitHub Action](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/variables)
- [Expresiones de GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/expressions)



## Retos Avanzados (opcional)
- En tu archivo de flujo de trabajo, define una variable de entorno para tu flujo de trabajo o trabajo con una cadena en él y pásala a uno de tus pasos de echo en job1.

- En tu archivo de flujo de trabajo, pasa el valor de una variable de entorno a una entrada de tu GitHub Action en job2.

[<  Reto Anterior](Challenge-03.md) - [Home](../README.md) - [Siguiente reto >](Challenge-05.md)
