# Reto 04 - Crear un Entorno de Despliegue

[< Reto Anterior](./Challenge-03.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-05.md)

## Introducción

Con la aplicación actualizada, ¡el refugio está listo para comenzar a configurar el despliegue! Han elegido usar Azure para alojar la aplicación. El sitio web se alojará en [Azure Container Apps](https://learn.microsoft.com/es-es/azure/container-apps/overview) y la base de datos en [Azure Cosmos DB para MongoDB](https://learn.microsoft.com/es-es/azure/cosmos-db/mongodb/introduction). 

El primer paso será asegurarte de que tienes acceso al repositorio de GitHub asignado. Este repositorio contiene toda la información necesaria para configurar y desplegar la aplicación en Azure. No necesitarás crear ni configurar el entorno por tu cuenta; simplemente tendrás permisos de lectura para acceder a la información relevante. Durante la introducción del reto, te proporcionaremos detalles sobre cómo acceder y utilizar este repositorio con la información de la cuenta de Azure que usarás. En un reto posterior, configurarás el despliegue continuo para el proyecto.

## Descripción

Para este reto, crearás un [GitHub workflow](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions) que utiliza un archivo [Azure Bicep](https://learn.microsoft.com/es-es/azure/azure-resource-manager/bicep/overview?tabs=bicep) para configurar los recursos necesarios en Azure. Para este reto, el grupo de recursos necesario ya está establecido y puedes encontrar toda la información relevante en el repositorio de GitHub asignado. Solo necesitarás configurar una identidad de servicio para otorgar los permisos necesarios a la acción y ejecutar la acción para crear los recursos adicionales.

La Configuración como Código (CaC), o configuración como código, es un enfoque para gestionar la configuración del sistema que implica definir los ajustes de configuración en archivos o scripts legibles por máquinas. Esto permite una gestión más eficiente, automatizada y consistente de la configuración del sistema, ya que los cambios pueden realizarse y desplegarse más fácilmente y con mayor control. Con la configuración como código, los ajustes de configuración se almacenan en archivos controlados por versiones, utilizando a menudo una sintaxis declarativa como YAML, JSON o HCL. Estos archivos pueden almacenarse junto con el código de la aplicación, facilitando la gestión de todo el ciclo de vida del desarrollo del software.

This challenge uses [Azure Bicep](https://learn.microsoft.com/azure/azure-resource-manager/bicep/overview?tabs=bicep), which is a domain specific language for defining Azure infrastructure. A Bicep file has already been created for you to use and will be provided by your coach. The Bicep file will:

Este desafío utiliza [Azure Bicep](https://learn.microsoft.com/es-es/azure/azure-resource-manager/bicep/overview?tabs=bicep), que es un lenguaje específico de dominio para definir la infraestructura de Azure. Ya se ha creado un archivo Bicep para que lo uses, lo purdes encontrar en el repositorio template que estamos usando. El archivo Bicep:

- Crea una instancia serverless de Azure Cosmos DB para MongoDB.
- Crea los recursos para soportar una Azure Container App.
- Crea la Azure Container App con una imagen predeterminada.
- Configurará la Azure Container App con la cadena de conexión para Azure Cosmos DB para MongoDB.

The Bicep file accepts one parameter named `prefixName`, which is to be set to 5 random alphanumeric characters. This will ensure all resources created have a unique name.

A medida que avances en el desafío, necesitarás utilizar la siguiente información y almacenarla en el repositorio según corresponda:

| Name                   | Description                                                         |
| ---------------------- | ------------------------------------------------------------------- |
| **location**           | Usa **westus** para la ubicación/región del grupo de recursos       |
| `prefixName`           | 5 caracteres alfanuméricos que crearás                 |
| **AZURE_CREDENTIALS**  | Las credenciales para usar en la gestión de recursos de Azure en el flujo de trabajo |
| **AZURE_SUBSCRIPTION** | El ID de tu suscripción a Azure                                  |
| **AZURE_RG**           | El nombre del grupo de recursos de Azure que creas                      |
| **AZURE_PREFIX**       | El prefijo que creaste anteriormente                                           |

    
## Criterios de Éxito

- Demuestra que has encontrado la información del grupo de recursos en Azure para los recursos de la aplicación en el repositorio asignado.
- Demuestra que has almacenado correctamente los valores necesarios para el flujo de trabajo en el repositorio, cifrando los valores que son sensibles.
- Demuestra que has creado un nuevo GitHub workflow llamado **create-azure-resources.yml** con las siguientes opciones:
  - El GitHub workflow puede ser ejecutado manualmente.
  - Lee el prefijo y otros parámetros desde secretos y variables.
- Demuestra que al navegar a la URL de la Aplicación Contenedor de Azure se muestra una pantalla con el mensaje **Welcome to Azure Container Apps**.

> **IMPORTANTE:** La imagen predeterminada configurada en el archivo Bicep tiene el mensaje apropiado configurado. **No** es necesario actualizar el código en la aplicación. Desplegarás la aplicación en un reto posterior.

## Recursos de Aprendizaje

- [¿Qué es la infraestructura como código (IaC)?](https://learn.microsoft.com/es-es/devops/deliver/what-is-infrastructure-as-code)
- [Entender las GitHub Actions](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions)
- [Guía de inicio rápido: implementación de archivos de Bicep mediante Acciones de GitHub](https://learn.microsoft.com/es-es/azure/azure-resource-manager/bicep/deploy-github-actions?tabs=CLI%2Cuserlevel)
- [Ejecutar un flujo de trabajo manualmente](https://docs.github.com/es/actions/using-workflows/manually-running-a-workflow)
- [GitHub Actions contexts](https://docs.github.com/es/actions/learn-github-actions/contexts)
- [Uso de secretos en Acciones de GitHub](https://docs.github.com/es/actions/security-guides/using-secrets-in-github-actions)
- [GitHub Actions variables](https://docs.github.com/es/actions/learn-github-actions/variables)
- [Create Actions secrets using GitHub CLI](https://cli.github.com/manual/gh_secret_set)
