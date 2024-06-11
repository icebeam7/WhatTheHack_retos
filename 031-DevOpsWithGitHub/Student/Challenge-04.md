# Challenge 04 - Your First GitHub Actions Workflow

[<  Reto Anterior](Challenge-03.md) - [Home](../README.md) - [Siguiente reto >](Challenge-05.md)

## Introduction

Automation is a critical part of an effective DevOps process incorporating elements like CI/CD, but also processes like IssueOps. GitHub Actions provides a platform for GitHub to respond to various event triggers to execute workflows.

Workflows are broken down into jobs that contain the automation steps to complete these jobs. These steps could be a simple CLI command or a pre-defined piece of automation defined as a GitHub Action from GitHub's extensive Marketplace.

Jobs can be run on Linux, Mac or Windows in the cloud on a hosted runner, or run on your own machines through a self-hosted runner. All the challenges today will use hosted runners, but your requirements after today may include the need for self-hosting or a mix of both.

Jobs can be run sequentially or in parallel. Sequential jobs provide the ability to define your workflow sequences, for example the need to build an application, then test it then deploy it. Whereas, parallel jobs allow the ability to scale-out sections of your workflow. For example build your application on x64 at the same time as ARM or, test you application on Chrome at the same time as Firefox.

Common workflows are defined for CI/CD type processes, but the flexibility of GitHub actions to respond to an extensive range of GitHub events enables many other possibilities such as the ability to execute a workflow based on a issue being created in your project.

## Description

This challenge will see us using GitHub Actions to write your first workflow. This workflow will start with a single job triggered by manual event, being expanded on to have a second job and an additional event trigger.

- Create a GitHub workflow in a `.github/workflows` directory (`first-workflow.yml`) that runs manually (*not* triggered by a push or pull request).

- To the workflow add a first job called job1 with two steps within it. The steps should be simple CLI commands to echo out step1 and step2 as applicable

- Trigger the workflow you created to run from GitHub. Check the log file for the workflow run to see your job executed and emitted from the echo statements as expected.

- Add a second job called job2 to your workflow yaml file. In this job add a step, but have this step call a GitHub Action from the GitHub Marketplace. A nice easy and fun example here may be to use something simple like 'Cowsays' which takes an input of a string that it uses to emit an ascii art cow into the workflow logs, however feel free to explore the marketplace for any action that you want to incorporate. 

  **NOTE:** When you look at an Action in the marketplace, note in the Links section on the right the repository link to a public repository with the code that backs that action.

- Execute your workflow again ensuring both jobs run as expected. 
  
  **NOTE:** These jobs have run in parallel.

- Amend your workflow yaml so that job2 will run sequentially after job1 completes. Execute the workflow again to test the sequence.

- Finally amend your workflow yaml file with an additional trigger that will fire when an issue is created.

## Success Criteria

- Be able to execute your first workflow from a manual trigger or an issue being created.
- Be able to see output from all the steps in the two jobs.
- The two jobs run now run sequentially with job2 running after job1 completes.
- job2 successfully runs a GitHub Action from the marketplace

## Learning Resources

- [Understanding GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/understanding-github-actions)
- [Essential features of GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/essential-features-of-github-actions)
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
- [Manually trigger a workflow](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch)
- [Events that trigger workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)
- [GitHub Action Variables](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/variables)
- [GitHub Actions Expressions](https://docs.github.com/en/enterprise-cloud@latest/actions/learn-github-actions/expressions)


## Advanced Challenges (optional)
- In your workflow file define an environment variable for your workflow or job with a string in it and pass it into one of your echo steps in job1.

- In your workflow file pass the value from an environment variable into an input of your GitHub Action in job2 

[<  Reto Anterior](Challenge-03.md) - [Home](../README.md) - [Siguiente reto >](Challenge-05.md)

--

# Reto 04 - Tu Primer Flujo de Trabajo con GitHub Actions

[< Reto Anterior](Challenge-03.md) - [Inicio](../README.md) - [Siguiente Reto >](Challenge-05.md)

## Introducción

La automatización es una parte fundamental de un proceso DevOps efectivo que incorpora elementos como CI/CD, pero también procesos como IssueOps. GitHub Actions proporciona una plataforma para que GitHub responda a varios desencadenantes de eventos para ejecutar flujos de trabajo.

Los flujos de trabajo se desglosan en trabajos que contienen los pasos de automatización para completar estos trabajos. Estos pasos pueden ser un simple comando de CLI o una pieza de automatización predefinida definida como una GitHub Action del extenso Marketplace de GitHub.

Los trabajos pueden ejecutarse en Linux, Mac o Windows en la nube en un runner alojado, o ejecutarse en tus propias máquinas a través de un runner autohospedado. Todos los desafíos de hoy utilizarán runners alojados, pero tus requisitos después de hoy pueden incluir la necesidad de auto-hospedaje o una combinación de ambos.

Los trabajos pueden ejecutarse secuencialmente o en paralelo. Los trabajos secuenciales proporcionan la capacidad de definir tus secuencias de flujo de trabajo, por ejemplo, la necesidad de compilar una aplicación, luego probarla y luego implementarla. Mientras que, los trabajos en paralelo permiten la capacidad de escalar secciones de tu flujo de trabajo. Por ejemplo, compilar tu aplicación en x64 al mismo tiempo que ARM o, probar tu aplicación en Chrome al mismo tiempo que en Firefox.

Los flujos de trabajo comunes se definen para procesos tipo CI/CD, pero la flexibilidad de las acciones de GitHub para responder a una amplia gama de eventos de GitHub permite muchas otras posibilidades, como la capacidad de ejecutar un flujo de trabajo basado en la creación de un issue en tu proyecto.

## Descripción

Este desafío nos llevará a usar GitHub Actions para escribir tu primer flujo de trabajo. Este flujo de trabajo comenzará con un solo trabajo desencadenado por un evento manual, ampliándose para tener un segundo trabajo y un desencadenante de evento adicional.

- Crea un flujo de trabajo de GitHub en un directorio `.github/workflows` (`first-workflow.yml`) que se ejecute manualmente (*no* desencadenado por un push o pull request).

- En el flujo de trabajo, agrega un primer trabajo llamado job1 con dos pasos dentro de él. Los pasos deben ser comandos simples de CLI para mostrar step1 y step2 según corresponda.

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

[< Reto Anterior](Challenge-03.md) - [Inicio](../README.md) - [Siguiente Reto >](Challenge-05.md)