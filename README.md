# WebGL StarterPack 📦

Punto de partida para el desarrollo de proyectos con WebGL, aprovechando el poder de [Webpack](https://webpack.js.org) y las ultimas tecnologías web.

#### Requisitos
- [npm](https://www.npmjs.com/get-npm)

#### Instalación

1. Descargar el [zip del repositorio](https://github.com/AgustinBrst/WebGL-StarterPack/archive/master.zip).
2. Descomprimirlo donde se quiera que quede el proyecto.
3. Desde la carpeta del proyecto ejecutar `npm install` para instalar todas las dependencias.

#### Uso

El proyecto presenta los siguientes comandos:

- __`npm run dev`__ corre un servidor local en [`http://localhost:8080/`](http://localhost:8080/) y lo accede con el buscador por defecto, recompilando y refrescando su contenido automáticamente (i.e. [live reloading](#live-reloading)).

- __`npm run build`__ compila el proyecto y deja los archivos generados en la carpeta `dist/`, listos a ser publicados en un servidor (para la version final usar el comando siguiente).

- __`npm run production`__ compila el proyecto y deja los archivos generados en la carpeta `dist/`, esta vez aplicando una serie de optimizaciones teniendo en cuenta que ésta es la version que accederá el usuario final (minificación de javascript, etc).

Durante el desarrollo se trabaja sobre la carpeta `src/`, donde se encuentra el archivo raíz `index.js`, el `html` y assets que se usaran en el proyecto. Ese archivo raíz es el que usa Webpack como punto de partida para construir su grafo de dependencias y compilar el proyecto para su acceso via el servidor local o la carpeta `dist/` mencionada. Webpack es un herramienta excelente y se recomienda la lectura de al menos sus [conceptos básicos](https://webpack.js.org/concepts/).

## Algunas características 📄

#### Conversión de Javascript ES6 con [Babel](https://babeljs.io)

Podes usar las características de Javascript más recientes, Babel se encarga de convertirlo para que sea compatible con cualquier buscador.

![](./docs/babel.png)

#### Live Reloading

Ante cualquier cambio en un archivo el buscador se refresca automáticamente. Chau `Ctrl + F5`.

<img style="border-radius: 5px;" src="./docs/liveReloading.gif">

#### Shaders / Texturas / Modelos 3D en su lugar

Assets en sus carpetas correspondientes sin cadenas de strings enormes, shaders en el html, etc.

![](./docs/structure.png)

#### Autoprefixer para CSS

Se puede escribir CSS sin tener en cuenta en que buscador se va a abrir el proyecto, los prefijos necesarios para mejorar la compatibilidad se agregan solos.

![](./docs/autoprefixer.png)

#### Linting via [ESLint](https://eslint.org)

Detectá errores triviales antes de llegar a la consola del buscador (requiere soporte del editor - e.g. SublimeLinter para SublimeText).

![](./docs/eslint.png)

#### Conversion a base 64 para lidiar con CORS
Opción para convertir imágenes a base 64 agregando `-- --env.base64` al final de cualquiera de las opciones de ejecución (e.g. __`npm run dev -- --env.base64`__). 

> ⚠️ La conversion es innecesaria si al proyecto se lo va a publicar en un servidor, cumple la función de esquivar las restricciones definidas en varios buscadores y facilita el compartir proyectos (con abrir el `.html` alcanza) pero puede generar archivos `.js` muy grandes (pensar que las imágenes que estarían en una carpeta `assets` pasan a formar parte del código en forma de texto)
