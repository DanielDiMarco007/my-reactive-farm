## Estructura del proyecto

ctive-farm/
│
├─ public/
│
├─ src/
│  ├─ assets/                # Imágenes, íconos o JSON local
│  │   └─ animals.json
│  │
│  ├─ components/            # Componentes reutilizables y visuales
│  │   ├─ Alert.jsx          # Mensajes de error, éxito o información
│  │   ├─ Loader.jsx         # Indicador de carga
│  │   ├─ Layout.jsx         # Contenedor principal de la app
│  │   ├─ AnimalCard.jsx     # Muestra datos de un animal individual
│  │   ├─ AnimalList.jsx     # Renderiza la lista de animales
│  │   └─ AnimalForm.jsx     # Formulario controlado con validaciones
│  │
│  ├─ pages/                 # Vistas o pantallas principales
│  │   └─ Farm.jsx           # Página principal (usa useEffect + lógica)
│  │
│  ├─ services/              # Comunicación con la API (Axios o Fetch)
│  │   └─ animalsApi.js
│  │
│  ├─ hooks/ (opcional)      # Custom hooks para lógica reutilizable
│  │   └─ useFetchAnimals.js
│  │
│  ├─ App.jsx                # Enrutador principal o punto de entrada de componentes
│  ├─ main.jsx               # Renderiza la app dentro del root DOM
│  ├─ index.css              # Estilos globales (reset, tipografía, colores)
│  └    ─ variables.css (opcional) # Paleta, dark mode, etc.
│
├─ package.json
├─ vite.config.js
└─ README.md


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

-----------------------
|## Cuestionario React|
-----------------------
¿Cuál es la diferencia entre un componente presentacional y un componente de página en React? Da ejemplos usando archivos del proyecto.?

Respuesta: 














