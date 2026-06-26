# sesión 11 - 26/06

# Sonido en p5.js (loadSound) y Síntesis de Audio — Introducción a la programación en p5.js

---

## Sonido en p5.js — `loadSound()`

### Paso 1 — Subir sus sonidos a p5

1. Hacer clic en la pequeña flecha hacia la derecha (`>`) ubicada en la esquina superior izquierda del editor (debajo del botón de *Play*). Esto abrirá el menú de archivos laterales.
2. Hacer clic en el icono de **+** o el menú desplegable junto a *Files*.
3. Seleccionar **Upload file** (Subir archivo).
4. Arrastrar el archivo de sonido.
   Formatos recomendados: `.mp3` o `.wav`
5. **Recomendación:** usar nombres de archivo cortos, en minúsculas y sin espacios. Hacer una carpeta llamada `ASSETS`.

### Paso 2 — Declarar y precargar el sonido (`function preload`)

1. Creamos una variable global al inicio del código para guardar nuestro sonido.
2. Usamos la función `function preload()`, inicializamos nuestra variable y cargamos el sonido con `loadSound()`.

```javascript
let miSonido;

function preload() {
  miSonido = loadSound('SONIDOS/beyonce.mp3');
}
```

### Paso 3 — Activar mi sonido

Le damos play al sonido en el `function setup` con:

Con esta instrucción, el sonido va a comenzar cuando le demos play a nuestro sketch.

```javascript
let miSonido;

function preload() {
  miSonido = loadSound("SONIDOS/beyonce.mp3");
}

function setup() {
  createCanvas(400, 400);
  miSonido.play();
}

function draw() {
  background(random(255), random(255), random(255));
}
```

 Ejemplo: https://editor.p5js.org/PoliMujica/sketches/lGzqNdYKy

### Lo ideal es activar mi sonido con un `mousePressed`

```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}

function mousePressed() {
  // Si el sonido no se está reproduciendo, lo activa
  if (!miSonido.isPlaying()) {
    miSonido.play();
  }
}
```

---

## ¿Cómo controlar mi sonido?

### Métodos de control de sonido

- `nombreVariable.play()`: reproduce el sonido una vez.
- `nombreVariable.loop()`: reproduce el sonido en bucle infinito.
- `nombreVariable.stop()`: detiene el sonido por completo.
- `nombreVariable.pause()`: pausa el sonido en el segundo actual.
- `nombreVariable.setVolume(valor)`: modifica el volumen. Recibe un número entre 0.0 (silencio) y 1.0 (volumen máximo).
- `nombreVariable.rate(valor)`: modifica la velocidad de reproducción. 1.0 es normal, 0.5 es la mitad de velocidad (suena más grave) y 2.0 es el doble (suena más agudo).

### Métodos de consulta o estados del sonido

- `nombreVariable.isPlaying()`: devuelve `true` si el sonido está sonando en este momento y `false` si no.
- `nombreVariable.isPaused()`: devuelve `true` si el sonido fue congelado con `pause()`.
- `nombreVariable.isLooping()`: devuelve `true` si el sonido está configurado para repetirse en `loop()`.
- `nombreVariable.currentTime()`: devuelve el segundo exacto en el que va la reproducción (ej: 12.45).
- `nombreVariable.duration()`: devuelve la duración total del archivo de audio en segundos (ej: 180.0).
- `nombreVariable.getVolume()`: devuelve el nivel de volumen actual del reproductor (un número entre 0.0 y 1.0).
- `nombreVariable.getRate()`: devuelve la velocidad de reproducción actual (ej: 1.0 para normal, 2.0 para el doble).

---

## Desafío: Radio Play / Pause

 Soluciones desafío:
- https://editor.p5js.org/PoliMujica/sketches/ouvJaCPQj
- https://editor.p5js.org/PoliMujica/sketches/ymB8_JKem

---

## Ejemplo: Beyoncé Game

 https://editor.p5js.org/PoliMujica/sketches/FyCvI7vbc

---

## Ejemplo: Piano Pad

- **Sin optimizar:** https://editor.p5js.org/PoliMujica/sketches/J7Ke6QogL
- **Optimizado:** https://editor.p5js.org/PoliMujica/sketches/LrtntncIA
- **Teclado clásico:** https://editor.p5js.org/PoliMujica/sketches/UDQ92bgRn

---

## Síntesis de audio — `p5.sound()`

### 3 componentes de un sintetizador básico

**El Oscilador (`p5.Oscillator`):** es el motor que genera el sonido. Puede tener distintas "formas de onda" que cambian el timbre del sonido:
- `'sine'` (onda senoidal o sinusoidal: un sonido suave, como una flauta).
- `'triangle'` (onda triangular: sonido intermedio).
- `'sawtooth'` (onda de diente de sierra: un sonido brillante y rasposo, como de sintetizador de los 80).
- `'square'` (onda cuadrada: sonido retro, tipo videojuego de 8 bits).

**La Frecuencia (Frequency):** controla qué tan rápido vibra la onda. Matemáticamente, a mayor frecuencia, el sonido es más agudo; a menor frecuencia, es más grave. Se mide en Hertz (Hz).

**La Amplitud (Amplitude):** controla la altura de la onda, lo que percibimos como el volumen. Va de 0.0 (silencio) a 1.0 (máximo).

 Recursos para explorar síntesis:
- https://learningsynths.ableton.com/
- https://learningsynths.ableton.com/en/playground

### Ejemplo sintetizador básico

Sintetizador modular con controles de frecuencia (Hz), amplitud (%) y selector de tipo de onda (senoidal, triangular, sierra, cuadrada), más un botón de encender/apagar.

 https://editor.p5js.org/PoliMujica/sketches/FhD6y43H7

---

## Lista de tutoriales de sonido
Playlist "p5.js Sound Tutorial" (The Coding Train, 11 vídeos): https://www.youtube.com/playlist?list=PLRqwX-V7Uu6aFcVjlDAkkGIixw70s7jpW

