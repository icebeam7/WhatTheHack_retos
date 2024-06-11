# Reto 05 - Infraestructura como Código (IaC)

[<  Reto Anterior](Challenge-04.md) - [Home](../README.md) - [Siguiente reto >](Challenge-06.md)

## Introducción

¡Ahora que tenemos algo de código, necesitamos un entorno para desplegarlo! El término Infraestructura como Código (IaC) se refiere al uso de plantillas (código) para crear repetidamente y de manera consistente los entornos de desarrollo, prueba y producción (infraestructura). Podemos automatizar el proceso de despliegue de los servicios de Azure que necesitamos con una plantilla de Azure Resource Manager (ARM) invocada desde la automatización en un flujo de trabajo de GitHub Actions.

Revisa los siguientes artículos:

- [Descripción general de Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview)
- [Crear una plantilla de Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/how-to-create-template)


## Descripción

Usaremos GitHub Actions para automatizar el despliegue de nuestra infraestructura de Azure. Para nuestra aplicación, desplegaremos 3 entornos: `dev`, `test` y `prod`. Cada entorno tendrá su propia aplicación web, sin embargo, todos nuestros entornos compartirán un solo grupo de recursos, un plan de App Service, una instancia de Application Insights y un registro de contenedores de Azure.

**NOTA:** En despliegues reales, es probable que no compartas todos estos recursos.

- Revisa la plantilla Bicep. Observa cómo está configurada para crear un plan de App Service, una aplicación web, Application Insights y un registro de contenedores de Azure en tu grupo de recursos.

- Observa cómo el archivo Bicep utiliza la función `uniqueString` para crear nombres únicos para tus recursos. Esta función no es aleatoria, sino una función hash sobre el ID de tu grupo de recursos para proporcionar una cadena de 13 caracteres consistente pero probablemente única que es útil para evitar conflictos de nombres en Azure.

- Observa que el entorno y la ubicación se definen como parámetros que tienen valores predeterminados pero pueden ser anulados. Podrás usar esto dentro del desafío para suministrar otros nombres como `test` y `prod` para crear otros recursos que representen diferentes entornos de despliegue.

- Las credenciales para iniciar sesión en Azure se encuentran en el repositorio que te compartimos. En este repositorio podrás encontrar toda la información necesaria, incluyendo las credenciales y el nombre del grupo de recursos.

- Crea un secreto a nivel de repositorio de GitHub para almacenar las credenciales de inicio de sesión anteriores.

- Crea una variable de configuración a nivel de repositorio de GitHub para almacenar el nombre del grupo de recursos de Azure.
  **CONSEJO:** Si encontraste la página para encontrar secretos para acciones, verás otra pestaña en el mismo lugar para ingresar variables de configuración a nivel de repositorio.

- Crea un nuevo flujo de trabajo de GitHub (`deploy.yml`) que se ejecute con un desencadenante manual (*no* desencadenado por un push o pull request).

- Configura tu flujo de trabajo para lograr lo siguiente:
  - Usa el ervice principal para iniciar sesión en Azure usando tus valores de secreto.
  - Usa la acción "Deploy Azure Resource Manager (ARM) Template" para llamar a la plantilla Bicep en tu repositorio.
  **NOTA:** El nombre es un poco confuso aquí, ya que esta acción admite tanto ARM como Bicep como archivo de plantilla. Esto se debe a que Bicep es una abstracción transparente de ARM. Para obtener más detalles, consulta este [artículo](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview?tabs=bicep).

- Ejecuta manualmente tu flujo de trabajo. Cuando tu flujo de trabajo se complete correctamente, ve al portal de Azure para ver el entorno `dev`.


Si todo funcionó, vamos a llamar nuevamente a la plantilla Bicep, pero anularemos el parámetro `environment` en la plantilla Bicep suministrando el valor de `test` para anular el valor predeterminado `dev` que se usó antes.

- Vuelve a ejecutar el flujo de trabajo. Cuando tu flujo de trabajo se complete correctamente, ve al portal de Azure para ver el nuevo App Service `test`.


- Finalmente, queremos recursos que representen la producción, así que reemplaza el valor `test` suministrado para tu variable de entorno anulada y cambia esto a `prod` y vuelve a ejecutar el flujo de trabajo. Cuando tu flujo de trabajo se complete correctamente, ve al portal de Azure para ver que se ha creado el nuevo App Service `prod`.

Deberías ver ahora los tres entornos en Azure.


## Criterios de Éxito

- Tu flujo de trabajo `deploy.yml` se completa sin errores y anula el parámetro `environment` al llamar a la plantilla Bicep.
- Tu grupo de recursos contiene 6 recursos: 3 App Services (dev, test, prod), 1 Application Insights, 1 plan de App Service y 1 registro de contenedores.

## Recursos de Aprendizaje

- [¿Qué es Infraestructura como Código?](https://docs.microsoft.com/en-us/azure/devops/learn/what-is-infrastructure-as-code)
- [Secretos en GitHub Actions](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- [Variables de Configuración en GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository)
- [Desplegar plantillas Bicep y Azure Resource Manager usando Git

## Desplegar plantillas Bicep y Azure Resource Manager usando GitHub Actions](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-github-actions)
- [Anulación de parámetros de plantillas ARM](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-cli#parameters)

## Retos Avanzados (opcional)

En lugar de cambiar la variable de entorno para cada entorno que queremos crear en el deploy.yaml, puedes configurar el flujo de trabajo para solicitar al usuario que ingrese el nombre del entorno antes de que se ejecute el flujo de trabajo, eliminando la necesidad de codificar el nombre del entorno.

- Configura tu flujo de trabajo para recopilar el nombre del entorno como una [entrada de flujo de trabajo](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#onworkflow_callinputs) y usa ese valor para anular el parámetro environment al llamar a la plantilla Bicep.

**NOTA**: Si estás interesado en aprender más sobre Infraestructura como Código, hay múltiples [What the Hacks](https://aka.ms/wth) que lo cubren con mayor profundidad:

   - [Infraestructura como Código: Bicep](https://microsoft.github.io/WhatTheHack/045-InfraAsCode-Bicep/)
   - [Infraestructura como Código: Plantillas ARM y PowerShell DSC](https://microsoft.github.io/WhatTheHack/011-InfraAsCode-ARM-DSC/)
   - [Infraestructura como Código: Terraform](https://microsoft.github.io/WhatTheHack/012-InfraAsCode-Terraform/Student/)
   - [Infraestructura como Código: Ansible](https://microsoft.github.io/WhatTheHack/013-InfraAsCode-Ansible/Student/)
    
[<  Reto Anterior](Challenge-04.md) - [Home](../README.md) - [Siguiente reto >](Challenge-06.md)