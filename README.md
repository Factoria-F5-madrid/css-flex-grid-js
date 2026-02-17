# Taller de Flex,Grid en CSS e introducción a Javascript

En este repositorio encontrarás un ejercicio práctico para aprender y practicar las propiedades **Grid y Flex** de CSS, además de un primer acercamiento a javascript. Este taller te permitirá estructurar un diseño utilizando un sistema de cuadrícula flexible y adaptativo.

## 🧰 ¿Qué contiene este repositorio?

- **index.html**: Este archivo ya incluye la estructura básica del diseño con las cajas y el contenido listo para estilizar.
- **style.css**: Aquí encontrarás los estilos aplicados a las cajas y al diseño general.
- **script.css**: En este archivo encontrarás el script para lograr el menú hamburguesa en modo responsive

### 🗂️ Ramas del repositorio

- **main**: Contiene el ejercicio sin resolver, listo para que lo completes.
- **solution**: Contiene el archivo `style.css` y `script.js` ya resuelto, con el código completo aplicado.

## ✨ Conceptos básicos sobre Grid

- **Grid-template-columns**: Define el número y tamaño de las columnas en el contenedor de la cuadrícula.
- **Grid-template-rows**: Define el número y tamaño de las filas en el contenedor de la cuadrícula.
- **Grid-area**: Asigna áreas específicas dentro de la cuadrícula para cada elemento.
- **Grid-gap**: Añade espacio entre las filas y columnas.

## 🚀 Instrucciones

1. Quédate en la rama `main` para realizar el ejercicio sin resolver.
2.	Abre el archivo index.html en tu navegador para visualizar la estructura inicial.
3.	Crea un archivo `style.css` y vincúlalo con el html y ve agregando una por una las secciones del CSS para observar cómo funcionan las propiedades de Flex y Grid.
```
/* CÓDIGO CSS */

* {
  margin: 0;
  padding: 0;
}

body {
  background: #e9ecf4;
  color: #000;
  font-family: "Roboto", sans-serif;
}

.contenedor {
  max-width: 1000px;
  margin: 20px auto;
  display: grid;
  grid-gap: 20px;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, auto);
  grid-template-areas:
    "nav nav nav"
    "contenido contenido sidebar"
    "bloque1 bloque1 bloque2 "
    "footer footer footer";
}

.contenido {
  background: #fff;
  padding: 20px;
  border-radius: 5px;
    grid-area: contenido;
}

nav {
  background: #ec9006;
  color: #fff;
  grid-area: nav;
  padding: 20px;
  border-radius: 5px;
}

.sidebar {
  grid-area: sidebar;
  background: #67db9e;
  display: flex;
  flex-direction: column;
  justify-content: top; 
  align-items: center; 
  padding: 20px;
  border-radius: 12px; 
}

.bloque {
  color: #ffff;
  text-align: left;
  flex-direction: column;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
  padding: 20px;
}

#bloque1 {
  grid-area: bloque1;
  background: #55a8fd;
}

#bloque2 {
  grid-area: bloque2;
  background: #1f6ab6;
}

footer {
  background: #4a4d50;
  color: #fff;
  grid-area: footer;
  padding: 20px;
  border-radius: 5px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

@media screen and (max-width: 768px) {
  .contenedor {
    grid-template-areas:
      "nav nav nav"
      "contenido contenido contenido"
      "sidebar sidebar sidebar"
      "bloque1 bloque1 bloque1"
      "bloque2 bloque2 bloque2"
      "footer footer footer";
  }
}
```
   
4.	Si necesitas ayuda o quieres comparar tu solución, cambia a la rama solution:
   ```git checkout solution```
  	
6. EXTRA: Agrega el script para que veas la magia de javascript!
   (Puedes agregarlo antes de cerrar la etiqueta de </body>
```
<script>
console.log("Hola mundito!");

const btn = document.querySelector("#cambiar-color"); // Selecciona por id

function random(number) {
  return Math.floor(Math.random() * (number + 1));
}

function changeBackground() {
  const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
}

btn.addEventListener("click", changeBackground);

document.addEventListener("DOMContentLoaded", function () {
  const boton = document.querySelector(".button-toggle");
  const menuLinks = document.querySelector(".menu");

  boton.addEventListener("click", function () {
    menuLinks.classList.toggle("open");
  });
});
</script>
``` 
