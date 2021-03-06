# Cypress - Cucumber - Screenplay

Proyecto de ejemplo donde se trata de implementar el patrón screenplay dentro de un proyecto de Cypress usando Cucumber como herramienta para BDD y tratando que sea de la manera más simple y usando las caracteristicas y herramientas provistas por Cypress. En este ejemplo la automatización es independiente a la aplicación.

## Cucumber
Para integrar Cypress con cucumber se hace uso de [cypress-cucumber-preprocessor](https://github.com/TheBrainFamily/cypress-cucumber-preprocessor). Para más información:

[Cypress](https://www.cypress.io/)

[Cucumber](https://cucumber.io/)

[cypress-cucumber-preprocessor](https://github.com/TheBrainFamily/cypress-cucumber-preprocessor#get-started)

---

## Instalación
Abrimos una consola y nos ubicamos en el directorio del proyecto. Ejecutamos el siguiente comando.

    npm install

## Ejecución

Antes de ejecutar el proyecto hay que cambiar dentro de la carpete cypress/fixtures el archivo **user.json** dos datos:

    "email": "camilo.bk.2010@gmail.com",
    "documentid":"1037574869",
    "firstname":"Juan Camilo",
    "lastname":"Hernandez Pulgarin",
    "cellphone":"3004442883",
    "localnumber":"2518956",
    "ext":"123",
    "jobposition":"Automation"

Es importante tener en cuenta que los comando que usamos para las ejecuciones estan configurados en el archivo package.json en el atributo scripts, a continuación los comandos y su equivalencia:

    cy:open: cypress open
    e2e: cypress run
    e2e-report: node scripts/cypress.js

### Ejecución desde el modo interactivo

Para abrir el Cypress Test Runner en modo interactivo ejecutamos el comando:

    npm run cy:open

Una vez abierto, seleccionamos el archivo (filename.spec.js) que queramos ejecutar. 

### Ejecución en navegador headless
Para ejecutar sobre la consola ejecutamos el comando:

    npm run e2e

### Reporte de pruebas
Para obtener un reporte de pruebas diferente al que nos aporta Cypress, ejecutamos el comando:

    npm run e2e-report

Se creará la carpeta mochawesome-report donde se encontrará el archivo **mochawesome.html**

## Arquitectura 

### Fixtures
Encontramos los datos estaticos usados en la automatización.

### Integration 
Encontramos los archivos .feature, es decir, nuestros casos de pruebas  y/o escenarios de pruebas.

La definición de los pasos debe estar en archivos .js (se recomienda que tenga el mismo nombre que el archivo feature), dentro de una carpeta que tenga el mismo nombre que el archivo .feature.

    Ejemplo

        path\cypress\integration\caracteristica.feature
        path\cypress\integration\caracteristica\caracteristica.js
    
### plugins
Para este ejemplo se usa, par el complementos de cucumber.

### Support
Permite agregar nuestros archivos de soporte, en este caso aca se incluiran los directorios necesarios para dar soporte al patrón screenplay.
*   interactions -> Representan las interacciones directas con la interfaz de usuario
*   taks -> Representan tareas que se realizan a nivel de proceso de negocio
*   ui -> Mapean los elementos de la interfaz de usuario

