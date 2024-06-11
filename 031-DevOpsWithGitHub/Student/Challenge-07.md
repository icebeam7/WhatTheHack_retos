# Reto 07 - Construir y Enviar una Imagen de Docker al Registro de Contenedores

[<  Reto Anterior](Challenge-06.md) - [Home](../README.md) - [Siguiente reto >](Challenge-08.md)


## Introducción

Ahora, necesitamos extender nuestro flujo de trabajo con pasos para construir una imagen de Docker y enviarla a Azure Container Registry (ACR). En el SIGUIENTE reto, configuraremos la Aplicación Web para que extraiga la imagen desde ACR.

Los contenedores son una excelente manera de empaquetar y desplegar aplicaciones de manera consistente en diferentes entornos. Si eres nuevo en los contenedores, hay 3 pasos clave para crear y publicar una imagen, que se describen a continuación. Debido a que este es un What The Hack enfocado en DevOps y no en contenedores, hemos tratado de hacer este desafío lo más sencillo posible.

1. `docker login` - necesitas iniciar sesión en el registro de contenedores al que enviarás tu imagen. Como puedes imaginar, no quieres que cualquiera publique una imagen en tu registro, por lo que a menudo se configura como un registro privado, requiriendo autenticación para enviar y extraer imágenes.

2. `docker build` - necesitas llamar a docker.exe (ejecutándose localmente en tu máquina o en tu servidor de construcción) para crear la imagen del contenedor. Un componente *crítico* de esto es el `Dockerfile`, que da instrucciones a docker.exe sobre cómo construir la imagen, los archivos a copiar, puertos a exponer y comandos de inicio.

3. `docker push` - una vez que hayas creado tu imagen de Docker, necesitas almacenarla en el registro de contenedores, que es nuestra ubicación centralizada y segura para almacenar imágenes de Docker. Docker soporta un comando push que copia la imagen de Docker al registro en el repositorio adecuado. Un repositorio es una forma lógica de agrupar y versionar imágenes de Docker.

## Descripción

En este desafío, construirás y enviarás una imagen de Docker a ACR:

- En la parte superior de tu archivo de flujo de trabajo, crea 4 variables de entorno:

    - `registryName` - la dirección completa del servidor de tu instancia de ACR. Establécela en "`registryName`.azurecr.io" - reemplazando `registryName` con el valor `<prefix>devopsreg` en tu archivo de plantilla ARM (línea #26). 
    - `repositoryName` - El repositorio a apuntar en el registro. Establécelo en "`wth/dotnetcoreapp`".
    - `dockerFolderPath` - La ruta a la carpeta que contiene el Dockerfile, un parámetro crítico. Necesitarás apuntar a la carpeta: `Application/src/RazorPagesTestSample`.
    - `tag` - Esto necesita ser un valor único cada vez, ya que se usa para versionar las imágenes en el repositorio. GitHub hace [variables de entorno](https://docs.github.com/en/free-pro-team@latest/actions/reference/context-and-expression-syntax-for-github-actions#github-context) disponibles que ayudan con esto. Establece `tag` en la variable de entorno [github.run_number](https://www.bing.com/search?q=%24%7B%7Bgithub.run_number%7D%7D&form=QBLH&sp=-1&pq=%24%7B%7Bgithub.run_number%7D%7D&sc=0-22&qs=n&sk=&cvid=D84DA66323DC4E14BD794F90FCFD90D3).

- Ve al Portal de Azure y obtén (1) el nombre de usuario, (2) la contraseña y (3) el servidor de inicio de sesión de tu instancia de ACR y guárdalos como secretos de GitHub (`ACR_USERNAME`, `ACR_PASSWORD`, `ACR_LOGIN_SERVER`).

- Agrega un segundo **trabajo** a tu flujo de trabajo de .NET Core existente. 

- Asegúrate de que el primer paso en tu segundo trabajo incluya `- uses: actions/checkout@v2`

- Para autenticarte en el registro, agrega un paso llamado `Docker login` con el siguiente comando `run`: `docker login $registryName -u ACR_USERNAME -p ACR_PASSWORD` - reemplazando ACR_USERNAME y ACR_PASSWORD con los secretos.

- Para construir tu imagen, agrega un paso llamado `Docker build` con el siguiente comando `run`: `docker build -t $registryName/$repositoryName:$tag --build-arg build_version=$tag $dockerFolderPath`

- Para enviar tu imagen a ACR, agrega un paso llamado `Docker push` con el siguiente comando `run`: `docker push $registryName/$repositoryName:$tag`

- Prueba el flujo de trabajo haciendo un pequeño cambio en el código de la aplicación (por ejemplo, agrega un comentario). Haz un commit, empuja, monitorea el flujo de trabajo y verifica que se haya construido una nueva imagen de contenedor, etiquetado de manera única y enviado a ACR después de cada ejecución exitosa del flujo de trabajo.

## Criterios de éxito

- Una nueva imagen de contenedor es construida, etiquetada de manera única y enviada a ACR después de cada ejecución exitosa del flujo de trabajo.

## Recursos de aprendizaje

- [Variables de entorno](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions#env)
- [Introducción a GitHub Actions](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/introduction-to-github-actions)
- [Comprensión de los filtros de ruta del flujo de trabajo](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions#onpushpull_requestpaths)
- [Autenticarse con un registro de contenedores de Azure](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-authentication#admin-account)
- [GitHub Actions para Azure](https://github.com/Azure/actions)

## Consejos

- Si tienes problemas para encontrar un punto de partida, intenta hacer clic en la pestaña 'Actions' de tu repositorio de GitHub.
- ¡Aprovecha las plantillas de flujo de trabajo preconstruidas si encuentras una que pueda funcionar!

## Desafíos avanzados (opcionales)

- En este desafío, si el flujo de trabajo falla, se envía un correo electrónico al propietario del repositorio. A veces, es posible que desees registrar o crear un issue en GitHub cuando el flujo de trabajo falla.
    - Agrega un paso a tu flujo de trabajo para crear un issue en GitHub cuando haya una falla.



[<  Reto Anterior](Challenge-06.md) - [Home](../README.md) - [Siguiente reto >](Challenge-08.md)

