
# sesión 09 - 12/06

# Estados y Cámara Web — Introducción a la programación en p5.js

---

## ¿Cómo crear un sketch con estados diferentes?

La idea es manejar distintas "pantallas" (inicio, experiencia, final) dentro de un mismo sketch usando una variable de estado.

### Paso 1 — Crear y definir la variable de estado

Al principio del código (fuera de las funciones), se crea una variable que guarda en qué pantalla estamos. Empieza en `0`.

​```javascript
let estado = 0; // 0 = Inicio, 1 = Experiencia, 2 = Final
​```

### Paso 2 — Configurar el lienzo (`function setup`)

Se crea el lienzo de fondo.

​```javascript
function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  textSize(24);
}
​```

### Paso 3 — Crear la estructura del estado (`function draw`)

Se usa un `switch`. Dependiendo del valor de la variable `estado`, el programa dibuja una cosa u otra.

​```javascript
function draw() {
  background(220);

  switch (estado) {
    case 0:
      pantallaInicio();
      break;
    case 1:
      pantallaExperiencia();
      break;
    case 2:
      pantallaFinal();
      break;
  }
}
​```

### Paso 4 — Programar visualmente cada estado (funciones propias)

Se crean las funciones definidas en el paso anterior. Cada una tiene un diseño y color distinto para notar el cambio.

​```javascript
function pantallaInicio() {
  background(135, 206, 250); // Azul claro
  fill(0);
  text("ESTADO 0: INICIO", width / 2, height / 2 - 20);
  textSize(16);
  text("Haz clic para continuar", width / 2, height / 2 + 20);
}

function pantallaExperiencia() {
  background(144, 238, 144); // Verde claro
  fill(0);
  textSize(24);
  text("ESTADO 1: JUEGO / EXPERIENCIA", width / 2, height / 2 - 20);

  // Aquí puedes poner elementos interactivos, por ejemplo un círculo que sigue al mouse
  fill(255, 100, 100);
  ellipse(mouseX, mouseY, 40, 40);

  fill(0);
  textSize(16);
  text("Haz clic para terminar", width / 2, height / 2 + 40);
}

function pantallaFinal() {
  background(255, 182, 193); // Rosado claro
  fill(0);
  textSize(24);
  text("ESTADO 2: FINAL", width / 2, height / 2 - 20);
  textSize(16);
  text("Haz clic para volver al inicio", width / 2, height / 2 + 20);
}
​```

### Paso 5 — La lógica del cambio y el reinicio

Para pasar de un estado a otro y volver al comienzo, se usa la función `mousePressed()`. Cada clic aumenta la variable. Si llega a 3 (después del estado 2), vuelve a 0.

​```javascript
function mousePressed() {
  // Avanzamos al siguiente estado
  estado = estado + 1;

  // Si pasamos del último estado (2), reiniciamos a 0
  if (estado > 2) {
    estado = 0;
  }
}
​```

 Ejemplo en p5.js: https://editor.p5js.org/PoliMujica/sketches/9vHePO158

---


### 1. Interacción con el teclado

**1.1. Por barra espaciadora o Enter:**

​```javascript
function keyPressed() {
  if (key === ' ' || keyCode === ENTER) { // ' ' es el espacio
    estado = estado + 1;
    if (estado > 2) estado = 0;
  }
}
​```

**1.2. Por teclas específicas (ej. números):** la tecla `1` lleva al inicio, la `2` a la experiencia y la `3` al final.

​```javascript
function keyPressed() {
  if (key === '1') estado = 0;
  if (key === '2') estado = 1;
  if (key === '3') estado = 2;
}
​```

 https://editor.p5js.org/PoliMujica/sketches/4lzOYE8KL

### 2. Botones reales en la pantalla

En lugar de hacer clic en cualquier parte de la pantalla, se puede crear un botón real de HTML usando la librería de p5.js. Es mucho más profesional para menús.

​```javascript
let botonSiguiente;

function setup() {
  createCanvas(400, 400);

  // Creamos el botón y le ponemos texto
  botonSiguiente = createButton('Siguiente Pantalla');
  botonSiguiente.position(150, 350); // Posición en la pantalla

  // Cuando se haga clic en ÉSTE botón, se ejecuta la función cambiarEstado
  botonSiguiente.mousePressed(cambiarEstado);
}

function cambiarEstado() {
  estado = estado + 1;
  if (estado > 2) estado = 0;
}
​```

 https://editor.p5js.org/PoliMujica/sketches/peTm3oGty

### 3. Zonas de clic (botones dibujados con rect o ellipse)

Si no quieres usar botones de HTML y prefieres dibujar tus propios botones con `rect()`, puedes evaluar si el mouse estaba dentro de esa caja al hacer clic.

​```javascript
function mousePressed() {
  // Imaginemos un botón dibujado en X: 100, Y: 50, Ancho: 200, Alto: 50
  if (mouseX > 100 && mouseX < 300 && mouseY > 50 && mouseY < 100) {
    estado = estado + 1;
    if (estado > 2) estado = 0;
  }
}
​```

 https://editor.p5js.org/PoliMujica/sketches/iw-gjFhK8

### 4. Interacciones automáticas (por tiempo)

**Temporizador:** ideal para una pantalla de introducción (Splash Screen) que dura 3 segundos y pasa sola al menú.

​```javascript
// En el draw, si estás en el estado 0 y pasan 3 segundos
if (estado === 0 && millis() > 3000) {
  estado = 1; // Pasa automáticamente al estado 1
}
​```

 https://editor.p5js.org/PoliMujica/sketches/_AunxbPWQ

---

## Interacción con el mundo físico

## Cámara web

### createCapture(VIDEO);

 Referencia: https://p5js.org/reference/p5/createCapture/

1. **Crear la variable para la captura:** declarar una variable global que guardará el flujo de video de la cámara web.
2. **Inicializar la cámara en `function setup()`:** usamos el comando especial `createCapture(VIDEO)`, que le pide permiso al navegador para encender la cámara del computador. También definimos el tamaño con `captura.size(x,y);` y es muy importante agregar `captura.hide();` para esconder el video que HTML pone abajo por defecto.
3. **Dibujar la cámara en `function draw()`:** usamos la función `image()`. p5.js toma cada cuadro (frame) de la cámara y lo dibuja en el lienzo en tiempo real.

​```javascript
let captura; // Aquí se guardará el video de la cámara

function setup() {
  createCanvas(640, 480);

  captura = createCapture(VIDEO);
  captura.size(640, 480);
  captura.hide();
}

function draw() {
  background(0);

  // Dibujamos la captura en la posición (0,0)
  image(captura, 0, 0, width, height);
}
​```

 https://editor.p5js.org/PoliMujica/sketches/PhkuD7kWU

### Ejemplos cámara interactiva

| Ejemplo | Enlace |
|---|---|
| Filtros | https://editor.p5js.org/PoliMujica/sketches/sK_BYepGn — referencia `filter()`: https://p5js.org/reference/p5/filter/ |
| loadPixels | https://editor.p5js.org/PoliMujica/sketches/OVsazOghk — referencia `loadPixels()`: https://p5js.org/reference/p5/loadPixels/ |
| Pincel de píxeles | https://editor.p5js.org/PoliMujica/sketches/cYCPjuXft |
| Píxeles reaccionan al volumen del mic | https://editor.p5js.org/PoliMujica/sketches/L9QBzREF3 |
| On/Off | https://editor.p5js.org/PoliMujica/sketches/Xdk0YBVbQ |

---
