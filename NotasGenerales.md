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

## ¿Qué es el State en Vue.js? - Diferencias entre ref y reactive
El state (o estado) determina la situación actual de nuestra aplicación. Si un carrito de compras esta lleno o vacío, si un cliente aceptó un viaje o no, si un usuario esta autenticado o no, son ejemplos del estado de nuestra aplicación. 

El State (o estado) no es siempre igual; tiende a cambiar en base a las interacciones del usuario (clicks, formularios, navegar en diferentes páginas, etc).

Debido a que el State tiende a cambiar, Vue.js tiene un par de funciones que nos permitirán declararlo y sobretodo identificar cuando el state ha cambido. Estas 2 funciones son (ambas se importan de Vue) y solo estan disponibles en Composition API:


* Reactive: Reactive siempre es un objeto y para acceder a las propiedades es con un punto (.). Reactive es un objeto, que lo hace ideal cuando quieres agrupar datos, ¿Pero qué pasa con los arrays, booleans o string?, para ello utilizamos Ref que nos permite trabajar con estos tipos de datos.
```JS
import {reactive} from 'vue';

const libro = reactive({
    disponible: true,
    nombre: 'Algoritmos 3',
    precio: 349,
    ISBN: "0-7645-2641-3"
})

// Reescribir una propiedades
libro.disponible = false;

// Acceder a las propiedades
console.log(libro.disponible) // false
```

* Ref: Cuando declaras un Ref deberás colocar un valor inicial.
```JS
import {ref} from 'vue';

const clientes = ref([]);
const libro = ref({});
const auth = ref(false);
const mensaje = ref('Hola');

// Reescribir una propiedad
clientes.value.push(nuevoCliente);
auth.value = true;
mensaje.value = 'NuevoTexto';

// Acceder a las propiedades, veamos que seguido del nombre de la propiedad debemos colocar .value
console.log(clientes.value) // Proxy.
console.log(auth.value) // False.
console.log(mensaje.value) // 'Hola'.
```