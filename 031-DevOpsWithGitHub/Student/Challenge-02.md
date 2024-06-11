# Reto 02 - Configurar un Codespace

[<  Reto Anterior](Challenge-01.md) - [Home](../README.md) - [Siguiente reto >](Challenge-03.md)

## Introducción

Los entornos de desarrollo son fundamentales para garantizar que los equipos de desarrollo estén configurados para hacer su mejor trabajo. Actualmente, es probable que cada miembro de tu equipo tenga una configuración ligeramente diferente de su entorno (editor, extensiones, herramientas) instalada en su máquina local.

GitHub incluye la capacidad de crear un entorno de desarrollo basado en la nube llamado codespace que se configura mediante un archivo de código de contenedor de desarrollo (`devcontainer.json`) detallado dentro de un repositorio. El archivo detalla cómo debe suministrarse un entorno de desarrollo de manera consistente desde la nube a cada desarrollador del equipo que quiera crear uno de forma autoservicio. Esto puede incluir el editor, las extensiones y las herramientas que queremos tener disponibles.

Nuestro repositorio incluye una aplicación escrita en .NET que se desplegará en Azure usando Infraestructura como Código a través de un lenguaje llamado Bicep. Queremos configurar nuestro codespace para que tenga las herramientas incluidas para trabajar con .NET, ARM (infraestructura como código) y la CLI de Azure.

## Descripción

- Agrega un nuevo archivo devcontainer en tu repositorio, colocado en un directorio `.devcontainer` que defina tu codespace. Asegúrate de que tu archivo devcontainer se base en una imagen de Docker para .NET, notablemente "mcr.microsoft.com/devcontainers/dotnet:0-6.0" para la aplicación suministrada en el hackathon en .NET 6.0.

  **SUGERENCIA:** - La extensión de contenedores de desarrollo de VS Code tiene una característica que simplificará el proceso de creación de un archivo devcontainer para muchos escenarios, o el siguiente fragmento de código debería ser un buen comienzo para nuestro hackathon.

```json
{
  "name": "C# (.NET)",
  "image": "mcr.microsoft.com/devcontainers/dotnet:0-6.0",
  "features": {
    "ghcr.io/devcontainers/features/azure-cli:1": {
      "installBicep": true,
      "version": "latest"
    }
  }
}
```

- Configura tu devcontainer para agregar una característica para la CLI de Azure (el fragmento de código anterior incluye esto).

- Inicia un nuevo codespace en tu repositorio y prueba que .NET y Azure CLI estén disponibles.

## Criterios de Éxito

- Debes haber creado un `devcontainer.json` colocado en un directorio `.devcontainer`.
- Debes haber creado un codespace para proporcionar una instancia basada en la nube del entorno descrito en tu archivo devcontainer.
- Tu codespace debe tener herramientas disponibles tanto para .NET como para Azure CLI.


## Recursos de Aprendizaje
- [Descripción general de Codespaces](https://docs.github.com/en/codespaces/overview)
- [Introducción a devcontainers](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers)
- [Configuración de un proyecto C# (.NET) en Codespaces](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/setting-up-your-dotnet-project-for-codespaces)
- [Agregar características a tu devcontainer](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/configuring-dev-containers/adding-features-to-a-devcontainer-file?tool=webui)
- [Visual Studio Code Dev Containers en VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- [Extensión de Visual Studio Code Dev Containers](https://code.visualstudio.com/docs/devcontainers/create-dev-container)


## Retos Avanzados (opcional)
- Agrega a tu `devcontainer.json` detalles de una extensión para instalar en Visual Studio Code y tu Codespace para que esté disponible de forma predeterminada para todo tu equipo. Un ejemplo aquí puede ser GitHub Copilot (que puedes habilitar una prueba gratuita para obtener sugerencias de IA durante el evento) o la extensión de GitHub Actions de GitHub, ambas están disponibles junto con miles de otras en [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/vscode).
- Agrega un `postCreateCommand` a tu `devcontainer.json` que restaurará los paquetes de NuGet para la aplicación .NET en el directorio de la aplicación del repositorio.

[<  Reto Anterior](Challenge-01.md) - [Home](../README.md) - [Siguiente reto>](Challenge-03.md)