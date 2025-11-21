## Estructura del proyecto

 src
 ┣  components
 │  ┣  AnimalCard
 │  │  ┗  AnimalCard.jsx
 │  ┣  AnimalForm
 │  │  ┗  AnimalForm.jsx
 │  ┣  Layout
 │  │  ┣  Header.jsx
 │  │  ┗  Footer.jsx
 │  ┗  Loading.jsx
 │
 ┣  pages
 │  ┣  AnimalsPage.jsx
 │  ┗  CreateAnimalPage.jsx
 │
 ┣  api
 │  ┗  animalsApi.js
 │
 ┣  hooks
 │  ┗  useAnimals.js
 │
 ┣  utils
 │  ┗  validations.js
 │
 ┣  styles
 │  ┗  global.css
 │
 ┣  App.jsx
 ┣  main.jsx
 ┗  index.html
 |
 |
 |.env
 |.gitignore
 |eslint.config
 |index.html
 |
 |package
 |package-lock
 |vite.config
 |
 |



## manejo de estados (useState)

el useState permite gestionar la parte dinamica de la página.


## useEffect

el useEffect se encarga de cargar los animales desde la api, ymaneja el error por si no se cargan los animales


## El consumo de API con Axios y MockAPI

La api contiene la lista de animales que se muestran en la página a traves de Axios y usando el mockApi para generar los animales


## El manejo de formularios y validaciones.

Los formularios en el proyecto permiten crear animales nuevos y que al momento de crearlos se cumplan requisitos

## Tailwind

ayuda a ponerle estilos y que se vea presentable el proyecto
## resumen proyecto
My Reactive Farm es una aplicación construida con React que simula la administración de una granja digital. El usuario puede crear, listar y observar animales dentro de la granja, usando una interfaz sencilla, rápida y reactiva.

-------------------------------
|## Cuestionario React punto 2|
-------------------------------
 ## ¿Cuál es la diferencia entre un componente presentacional y un componente de página en React? Da ejemplos usando archivos del proyecto.?

Respuesta: 
un componente presentacional es un componente enfocado únicamente en mostrar la interfaz visual

ejemplo:
AnimalCard.jsx

Solo recibe un animal y lo renderiza.


 un componente de página contiene la lógica principal: carga de datos, llamadas a la API, manejo de errores y control de qué componentes mostrar.
 
 ejemplo:

Farm.jsx
Carga animales desde MockAPI usando getAnimals().

 ## ¿Para qué se utiliza useState en el proyecto? Menciona dos estados distintos y su función.

 useState se usa para manejar valores que cambian con la interacción del usuario y con la carga de datos desde la API.

 const [animals, setAnimals] = useState([]); 
 Guarda la lista de animales que viene desde la API MockAPI

 const [isLoading, setIsLoading] = useState(true);
 Indica si la app está cargando animales desde la API.

 ## ¿Cómo se usa useEffect para cargar datos desde MockAPI al inicio? Explica el flujo.

 En Farm.jsx, el proyecto usa useEffect para cargar la lista de animales apenas la página se monta.

El flujo es así:

Se monta el componente Farm.
useEffect se ejecuta con un array [] → significa “solo una vez”.
Pone loading en true.
Llama a getAnimals() desde animalsApi.js.
Si todo sale bien → setAnimals(data).
Si hay error → setLoadError("Failed to load animals…").
De cualquier forma → loading vuelve a false.

## ¿Cómo maneja el proyecto los estados de loading, error y lista vacía? ¿Qué se muestra al usuario en cada caso?

El proyecto implementa un patrón estándar para manejar el ciclo de carga de datos desde la API:

 Loading

Mientras la información se obtiene desde MockAPI, se muestra un mensaje o un componente de carga para evitar dejar la interfaz vacía.

 Error

Si ocurre un fallo durante la petición, se muestra un mensaje indicando que no fue posible obtener los datos.
Esto informa al usuario que hubo un problema de red o del servidor.

 Lista vacía

Si la API responde correctamente pero no existen animales registrados, se muestra un texto informando que no hay elementos en la lista.
Esto permite diferenciar entre "no cargó" y "cargó pero no hay datos".

## ¿Qué significa que un formulario sea controlado en React? Relaciónalo con el formulario del proyecto.

Un formulario controlado es aquel donde cada input está conectado directamente al estado de React.
El valor del campo depende de un useState, y cualquier cambio del usuario actualiza ese estado.
En My Reactive Farm, el formulario para crear animales usa este enfoque, lo que asegura que los datos estén siempre sincronizados con la interfaz.


## ¿Por qué es buena práctica separar la lógica de datos en archivos como animalsApi.js en vez de hacer peticiones dentro de los componentes?


Organizar las peticiones a la API en un archivo independiente ofrece varias ventajas:
Evita repetir código en distintos componentes.
Mantiene los componentes más limpios y enfocados en la interfaz.
Hace posible probar las funciones de la API de forma aislada.

## ¿Qué hace que AnimalCard sea un componente reutilizable? ¿Cómo se podría usar una tarjeta similar en otro contexto?

es reutilizable  porque Recibe todos sus datos por props.
-No contiene lógica dependiente de una página específica.
-No almacena estados locales que limiten su uso.
Con este mismo patrón, se puede reutilizar la tarjeta para otros contextos:
-Productos de una tienda.
-Perfiles de usuarios.
-Cursos o publicaciones.
-Artículos de blog.
Solo se deben cambiar los valores enviados por las props.

##  Elementos de accesibilidad presentes en el proyecto

El proyecto incorpora prácticas que mejoran la accesibilidad:

1. role="status"

Informa a tecnologías de asistencia que el contenido representa un mensaje de estado.

2. aria-live="polite"

Permite que los anuncios (como loaders o alertas) sean leídos automáticamente sin interrumpir al usuario.

3. Textos descriptivos en pantalla (<p>{message}</p>)

Aseguran que no solo haya indicadores visuales, sino también información clara para personas con discapacidad visual o cognitiva.

## Antes de agregar una funcionalidad nueva, ¿qué pasos debes pensar según la filosofía de React? (ej.: qué datos, qué estado, dónde vive la lógica)

primero decidir que tipo de dato quieres que sea, ya despues ver si lo vas poner como componente para poder reutilizarlo si nnecesidad de duplicar código 


## ¿Qué conceptos de React aprendidos en este proyecto podrías reutilizar en otro tipo de aplicación? Da al menos cuatro ejemplos.

-usar los componentes para una mejor administración de recursos en mi página web

-useState: Para manejar valores dinámicos como formularios, listas o contadores.

-useEffect: Para ejecutar lógica al cargar la página o cuando cambian dependencias.

-Consumo de APIs con Axios: Para enviar o recibir información desde cualquier backend.




















