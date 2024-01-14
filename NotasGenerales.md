## Single File Component (SFA) en Vue.js
Dentro de cada componente, encontraremos las etiquetas script, template y style se les conoce como Single File Components (SFA). En ellas realizaremos la separación de código de la siguiente manera:
* scripts: Logica de desarrollo.
* template: HTML que se mostrara en pantalla.
* style: CSS/Sass que tendra el componente.

## Recorrido por los directorios/archivos de Vue
* .vscode : Muestra recomendaciones en extensiones de VSCode.
* node_,modules : Dependencias utilizadas para el funcionamiento o desarrollo del proyecto.
* public : Contendo para los usuarios, ya sea imagenes, etc.
* src : Aquí escribiremos la mayoria de nuestro código.
    * assets : Se pueden almacenar imagenes e importarlas directamente en los componentes.
    * components : Aquí crearemos nuestros componentes.
    * App.vue : Componente principal.
    * main.js : Importa createApp para crear nuestra aplicación de Vue, a demás importa el archivo Style.css y App.vue para el funcionamiento inicial del proyexto.

## API Styles en VUE - Composition API y Options API
Los componentes de Vue.js se pueden escribir en 2 API's diferentes: CompositionAPI y Options API.

Options API está disponible desde Vue.js 2 mientras que Composition API desde la versión 2.7 y es la recomendada para proyectos con Vue 3.

* Options API : Con Options API se define la lógica de un componente utilizando una sintaxis de objeto.
* Composition API : Con Composition API se definen los componentes utilizado Imports (tanto para funciones de Vie como Librerías). 
    * Para utilizar esta opción solo debemos agregar la palabra setup a la etiqueta script del componente.
    * Composition API tiene 2 funciones para reactividad: reactive y ref.

Este curso utilizará Composition API ya que es más nuevo, se adapta mejor a la reutilización de código y es el que recomienda el equipo de Vue.