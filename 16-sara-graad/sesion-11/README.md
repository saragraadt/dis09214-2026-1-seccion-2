
# Sonido y Sintesis de Audio en p5.js

[cite_start]Este repositorio contiene un resumen practico y ejemplos sobre como integrar archivos de audio y generar sintesis de sonido utilizando la libreria p5.sound() en p5.js[cite: 3, 4, 122, 125].

---

## Guia Rapida: Cargar y Reproducir Audio

### 1. Subir el archivo al editor p5.js
1. [cite_start]Despliega el menu lateral de archivos (>)[cite: 8, 9].
2. [cite_start]Haz clic en el icono + y selecciona Upload file[cite: 10, 11].
3. [cite_start]Sube un archivo en formato .mp3 o .wav[cite: 12, 13].

[cite_start]Se recomienda usar nombres cortos, en minusculas, sin espacios y organizarlos dentro de una carpeta llamada ASSETS o SONIDOS[cite: 14, 23].

### 2. Estructura basica de codigo
[cite_start]El sonido se declara de forma global, se precarga en la funcion preload() y se activa mediante una interaccion en mousePressed()[cite: 41, 43, 76, 78, 79]:

```javascript
let miSonido;

function preload() {
  miSonido = loadSound('SONIDOS/beyonce.mp3');
}

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}

function mousePressed() {
  if (!miSonido.isPlaying()) {
    miSonido.play();
  }
}
