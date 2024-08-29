# Reto 03 - Integración continua y seguridad

[< Reto Anterior](./Challenge-02.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-04.md)

## Introducción

El refugio ha visto muchas noticias preocupantes sobre brechas de seguridad en diversas aplicaciones, incluidas las gestionadas por organizaciones sin fines de lucro. De hecho, las organizaciones que tradicionalmente pueden no haber invertido en infraestructura pueden ser objetivos populares para los atacantes. El refugio quiere asegurarse de que su aplicación no contenga vulnerabilidades que puedan ser explotadas.

## Descripción

Para este desafío, deberas configurar el escaneo para toda la [cadena de suministro de software](https://github.blog/2020-09-02-secure-your-software-supply-chain-and-protect-against-supply-chain-threats-github-blog/) de la aplicación. Específicamente, deseas escanear tu código en busca de problemas potenciales cuando se realiza un [pull request](https://docs.github.com/es/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) a la rama `main`. También quieres confirmar que los paquetes que utiliza el proyecto estén libres de vulnerabilidades conocidas. Finalmente, una vez que hayas configurado la seguridad, crearás un pull request con las actualizaciones de código que realizaste en el reto anterior.

El escaneo de vulnerabilidades, la ejecución de pruebas y la verificación de que el código compila típicamente se automatizan como parte de un proceso llamado integración continua (CI). La CI permite a los equipos validar rápidamente que el nuevo código no introduzca problemas en la base de código existente, mejorando tu capacidad para responder a las solicitudes de los clientes y reducir la sobrecarga de desarrollo. Para este hack, habilitarás [GitHub Advanced Security](https://docs.github.com/es/get-started/learning-about-github/about-github-advanced-security), que es una parte común de un proceso completo de CI.

## Tips

- En la pestaña **Settings**, localiza la opción **Code security and analysis** en el menú lateral. Activa las actualizaciones de seguridad de Dependabot y el análisis de CodeQL.
- Ahora, en el menú lateral **Branches** agrega una regla de protección de rama sobre `main` que requiera un pull request antes de hacer un merge y que requiera que se aprueben dos comprobaciones de estado antes de hacer merge: Dependabot y CodeQL (selecciona las que aparezcan, en caso de que no aparezca ninguna, continúa el reto e intenta este paso una hora más tarde).
- Crea la regla.
- Crea una rama si no lo has hecho ya. Haz un commit sobre la rama, sincroniza los cambios, genera un pull request hacia main. Observarás que aparecen algunas comprobaciones de estado. No necesitas esperar a que se completen, puedes continuar con el reto.

## Criterios de Éxito

- Demostrar que la [revisión de dependencias](https://docs.github.com/es/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review) está habilitada para el repositorio.
- Demostrar que el [escaneo de código](https://docs.github.com/es/code-security/code-scanning/introduction-to-code-scanning/about-code-scanning) está configurado para ejecutarse en todas los solicitudes de pull requests realizadas a `main`.
- Verificar que la rama `main` esté configurada para requerir pull requests, y que tanto el escaneo de código como la revisión de dependencias deben aprobarse para que se complete un merge.
- Demostrar que se ha realizado una solicitud de pull request a main y que todas las verificaciones han pasado.

> **IMPORTANTE:**  Realizarás el merge del PR en `main` en un reto posterior. 

## Recursos de Aprendizaje

- [Entender las GitHub Actions](https://docs.github.com/es/actions/learn-github-actions/understanding-github-actions)
- [Acerca del escaneo de código](https://docs.github.com/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)
- [Configurando el escaneo de código en un repositorio](https://docs.github.com/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/configuring-code-scanning-for-a-repository)
- [Acerca de la revisión de dependencias](https://docs.github.com/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review)
- [Configuración de la revisión de dependencias](https://docs.github.com/code-security/supply-chain-security/understanding-your-software-supply-chain/configuring-dependency-review)  
- [Acerca de las ramas protegidas](https://docs.github.com/es/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [Administrar una regla de protección de rama](https://docs.github.com/es/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule)
- [Utilizar el control de código fuente en tu codespace](https://docs.github.com/es/codespaces/developing-in-a-codespace/using-source-control-in-your-codespace)

## Tips

- Para este hackaton, primero habilita la revisión de dependencias para el repositorio, espera a que se generen los pull-request correspondientes a las actualizaciones de los paquetes con vulnerabilidades (deberían ser 3). Luego, puedes proceder a habilitar el escaneo de código.
- El motivo del orden anterior se debe a que con la configuración predeterminada de escaneo de código, éste no se ejecutará con los pull requests generados por la revisión de dependencias, ocasionando una advertencia. En caso de obtener la advertencia, simplemente ignórala y continúa con tu trabajo.

[< Reto Anterior](./Challenge-02.md) - **[Home](../README.md)** - [Siguiente reto >](./Challenge-04.md)