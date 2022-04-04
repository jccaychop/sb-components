# <b>REACT + TYPESCRIPT + STORYBOOK</b>

## Pasos previos
<hr>

- Vista previa del README.md

  ```
  Ctrl+Shift+V
  ```

- Desinstalamos react-scripts
  ```
  npm uninstall react-scripts
  ```

- Eliminar la carpeta public

- Dentro de la carpeta src, eliminamos:
  ```
  App.css
  App.test.tsx
  App.tsx
  index.css
  logo.png
  react-app-env.d.ts
  reportWebVitals.ts
  setupTests.ts
  ```

- El archivo index.tsx, debe de quedar:
  ```
  import React from 'react';
  import ReactDOM from 'react-dom';

  ReactDOM.render(
    <React.StrictMode>
      
    </React.StrictMode>,
    document.getElementById('root')
  );
  ```

<br>
<br>

## Instalacion de Storybook
<hr>

https://storybook.js.org/docs/react/get-started/install

- Add Storybook:
  ```
  npx sb init
  ```

- En el archivo package.json, debe de quedar:
  ```
  "scripts": {
      "start": "start-storybook -p 6006",
      "build": "build-storybook",
      "storybook": "start-storybook -p 6006",
      "build-storybook": "build-storybook"
    },
  ```

<br>
<br>

## Ejecutar Storybook
<hr>

- En la consola:
  ```
  npm run storybook 
  ```

- Por defecto nos muestra el puerto:
  ```
  http://localhost:6006/ 
  ```

<br>
<br>

## Despliegue de Storybook a servidores
<hr>

https://www.npmjs.com/package/http-server

- Abrir el package.json y verificamos lo siguiente:
  ```
  "build": "build-storybook",
  ```

- Entonces, ejecutamos:
  ```
  npm run build
  ```

- Vemos que se crea una carpeta:
  ```
  storybook-static
  ```

- <b>PASO OPCIONAL:</b> Si queremos que se cree la carpeta `storybook-static`, pero con el nombre `docs`, realizamos lo siguiente en el archivo `package.json`:
  ```
  "build": "build-storybook -o docs",
  ```

- Instalamos de manera global y con la consola en modo administrador
  ```
  npm install --global http-server
  ```
- Se recomienda cerrar la consola y volver a abrirla.

- Luego, en la consola, vamos a al ruta del storybook-static (o docs) y ejecutamos:
  ```
  http-server -o
  ```
- Y debe de abrirse una ventana del navegador con el proyecto

<br>

## Desplegando en Netlify

- Luego, abrimos netlify, y en al pestaña Sites, arrastramos la carpeta storybook-static (o docs).
- Esperamos unos segundos y se debe de crear nuestra pagina, la cual luego podemos modificar el nombre.

<br>

## Desplegando en Github y Github Pages
- Creamos un nuevo repositorio.
- En nuestro proyecto, inicializamos git:
  ```
  git init
  ```
- Abrimos el archivo .gitignore y agregamos:
  ```
    # production
    /build
    /storybook-static
    ```
- Renombramos la carpeta `storybook-static` a `docs`, si es que antes no lo hemos hecho.
- Realizamos el commit.
- Ejectamos los comandos para subir el repositorio a github.
- Luego de subirlo a github, seleccionamos Settings.
- CLic en `Pages`, luego en `Source` seleccionamos `main` y el directorio `docs`, luego clic en `Save`.
- Veririfcar que este marcado `Enforce HTTPS`
- Se debe de desplegar el proyecto.
  
<br>
<br>

## Nota:  
Si tenemos el `build`, con la carpeta `docs` de forma automatica, cada vez que hacemos un `commit` al proyecto, este se desplegará de forma automatica en `Github pages`.
