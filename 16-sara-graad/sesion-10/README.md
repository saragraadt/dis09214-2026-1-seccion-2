# sesión 10

  # Diseño Responsivo (windowResized) e Imágenes — Introducción a la programación en p5.js

---

## ¿Cómo crear un sketch que se adapte a diferentes tamaños de pantalla?

### Paso 1 — Crear un canvas con dimensiones dinámicas

Usaremos las variables integradas en el sistema: `windowWidth` y `windowHeight`. Estas variables leen constantemente el ancho y alto disponibles de la ventana del navegador.

```javascript
function setup() {
  createCanvas(windowWidth, windowHeight);
}
```

### Paso 2 — Crear un evento `windowResized()`

Si el usuario estira o encoge la ventana del navegador, el lienzo se adaptará al tamaño de la ventana en tiempo real.

```javascript
function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}
```

### Paso 3 — Usar valores relativos

p5.js actualiza las variables `width` y `height` automáticamente con el tamaño actual del lienzo. Entonces todos los valores de posición y tamaño que ocupemos los tenemos que pensar en relación proporcional a esas variables.

Usaremos fracciones y proporciones:
- Centro del lienzo: `(width / 2, height / 2)`
- A un cuarto de la pantalla en eje x: `(width * 0.25)`

> No del todo correctos. Ejemplos:
> - https://editor.p5js.org/PoliMujica/sketches/zc4NEOF0t
> - https://editor.p5js.org/PoliMujica/sketches/EjIGRHtFR

```javascript
function setup() {
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(240);

  fill(150, 150, 250);
  noStroke();
  rect(width * 0.05, height * 0.05, width * 0.2, height * 0.15);

  fill(250, 100, 100);
  ellipse(width * 0.5, height * 0.5, width * 0.2, height * 0.2);

  stroke(50);
  strokeWeight(width * 0.005);
  noFill();
  ellipse(width * 0.5, height * 0.5, width * 0.25, height * 0.25);

  fill(100, 200, 150);
  noStroke();
  triangle(
    width * 0.85, height * 0.1,
    width * 0.75, height * 0.25,
    width * 0.95, height * 0.25
  );
}
```

### Paso 4 — Incluir un factor de referencia

`referencia = min(width, height)`

Creamos una variable global (`referencia`) y la asignamos para que calcule el mínimo. Observa el ancho y el alto de la ventana, los compara, y se queda solo con el que sea más pequeño en ese momento.

```javascript
let referencia;

function setup() {
  createCanvas(windowWidth, windowHeight);
  referencia = min(width, height);
}

function draw() {
  background(240);

  let xCentro = width / 2;
  let yCentro = height / 2;

  // El diámetro será siempre el 40% del lado más corto de la ventana
  let diametro = referencia * 0.4;

  fill(250, 100, 100);
  noStroke();
  ellipse(xCentro, yCentro, diametro, diametro);
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
  referencia = min(width, height);
}
```

 Ejemplos:
- https://editor.p5js.org/PoliMujica/sketches/eK300f-Ac
- https://editor.p5js.org/PoliMujica/sketches/h7jZHn8al

### Paso 5 — Usar translate, push y pop

**Consejo para proyectos complejos:** en lugar de hacer matemáticas complejas en cada `rect()` o `ellipse()`, usamos `translate()` para "mover el origen del mundo". Y siempre utilizando `push()` y `pop()` para cada figura o elemento.

```javascript
let referencia;

function setup() {
  createCanvas(windowWidth, windowHeight);
  referencia = min(width, height);
}

function draw() {
  background(240);

  // 1. Rectángulo (Posicionado arriba a la izquierda)
  push();
  translate(width * 0.05, height * 0.05);
  fill(150, 150, 250);
  noStroke();
  rect(0, 0, referencia * 0.2, referencia * 0.15);
  pop();

  // 2. Círculos (Posicionados en el centro de la pantalla)
  let diametro = referencia * 0.25;
  push();
  translate(width / 2, height / 2);

  fill(250, 100, 100);
  noStroke();
  ellipse(0, 0, diametro, diametro);
}
```

Ejemplos:
- https://editor.p5js.org/PoliMujica/sketches/llkPe9bZ8
- https://editor.p5js.org/PoliMujica/sketches/qDjCOtTlB

---

## Desafío en clases — Bandera chilena diseño responsivo

 Solución 1: https://editor.p5js.org/PoliMujica/sketches/VItuFGt_x
 Solución 2: https://editor.p5js.org/PoliMujica/sketches/kfV_cR5Dz

---

## Agregar imágenes — `loadImage()`

### Paso 1 — Subir la imagen a p5

1. Hacer clic en la pequeña flecha hacia la derecha (`>`) ubicada en la esquina superior izquierda del editor (debajo del botón de *Play*). Esto abrirá el menú de archivos laterales.
2. Hacer clic en el icono de **+** o el menú desplegable junto a *Files*.
3. Seleccionar **Upload file** (Subir archivo).
4. Arrastrar la imagen o buscarla en el computador.
5. **Recomendación:** usar nombres de archivo cortos, en minúsculas y sin espacios. Hacer una carpeta llamada `ASSETS`.

### Paso 2 — Declarar y precargar la imagen (`function preload`)

1. Creamos una variable global al inicio del código para guardar la imagen.
2. Usamos la función dentro de `function preload()` y cargamos la imagen con `loadImage()`.

```javascript
let miImagen;

function preload() {
  miImagen = loadImage('assets/poli.jpg');
}
```

### Paso 3 — Dibujar y dimensionar en el draw

La imagen se dibuja usando la función `image()`. Esta función requiere mínimo 3 argumentos, pero acepta 5 si queremos controlar su tamaño de forma responsiva.

**Sintaxis:**
```
image(nombreVariableImagen, x, y, ancho, alto);
```

```javascript
let miImagen;

function preload() {
  miImagen = loadImage('assets/poli.jpg');
}

function setup() {
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(240);
  image(miImagen, 50, 50, 300, 200);
}
```
 Ejemplo: https://editor.p5js.org/PoliMujica/sketches/ewXN-4Jzt
 Ejemplo diseño responsivo: https://editor.p5js.org/PoliMujica/sketches/yQ5d0XMun

---

## Ejemplos avanzados de distorsión de imagen — `loadPixels()`

### Entrar en los píxeles

`loadPixels()` toma todos los píxeles de la pantalla (o de una imagen) y los carga en la memoria de acceso rápido (RAM). Se comunica directamente con la tarjeta gráfica píxel por píxel en tiempo real. Crea un "puente" temporal para que puedas analizar la información de forma masiva y fluida.

### Modificar los píxeles

**`get(x, y)` — Lectura (el "ojo")**
- **Función:** va a la coordenada exacta (x, y) y extrae el color de ese píxel.
- **Resultado:** devuelve un objeto de color o un arreglo con los cuatro canales esenciales: `[Rojo, Verde, Azul, Alfa]` (valores de 0 a 255).
- **Uso extra:** si lo usas sin coordenadas (`imagen.get()`), sirve para clonar o hacer una copia de respaldo completa del lienzo.

**`set(x, y, nuevoColor)` — Escritura (el "pincel")**
- **Función:** va a la coordenada (x, y) e inyecta un color nuevo, reemplazando por completo el color que existía ahí.
- **Resultado:** modifica el mapa de píxeles en la memoria interna, preparando el nuevo aspecto de la imagen.

**`updatePixels()` — La actualización**
- **Función:** toma todos los cambios que realizaste con `set()` y los sube de golpe a la pantalla.
- **¿Por qué es muy necesario?** `set()` no dibuja inmediatamente; solo guarda los cambios en un borrador secreto. `updatePixels()` es el comando que efectivamente "publica" y renderiza el resultado final en el lienzo para que el usuario pueda verlo.

### Ejemplos distorsión imagen

| Ejemplo | Enlace |
|---|---|
| Distorsión de píxeles — cambio a solo rojo | https://editor.p5js.org/PoliMujica/sketches/yX_ljcTGX |
| Distorsión de píxeles — efecto Aladino | https://editor.p5js.org/PoliMujica/sketches/jaEqYvHew |
| Distorsión de píxeles — onda seno | https://editor.p5js.org/PoliMujica/sketches/qnqADHqrC |

### Pattern Generator Interface

- https://editor.p5js.org/tick-nopp/sketches/yRScEGlul
- https://editor.p5js.org/tick-nopp/sketches/4nJg1CQDM
- https://editor.p5js.org/tick-nopp/sketches/AGYdsQWGc

### Tutoriales — Images

 https://youtube.com/playlist?list=PLRqwX-V7Uu6YB9x6f23CBftiyx0u_5sO9&si=teEGKAA9oMZw_4ll
