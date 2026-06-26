# Diseño Responsivo (windowResiezed) 
# ¿CÓMO CREAR UN SKETCH CON ESTADOS DIFERENTES? 
- Paso 1. CREAR Y DEFINIR VARIABLE ESTADOS
(windowWidth, windowHeight)
1.  Al principio de tu código (fuera de las funciones), debes crear una
variable que guarde en qué pantalla nos encontramos. Empezará en 0.


- Paso 2. CONFIGURAR EL LIENZO (function setup)
2. Creamos el lienzo de fondo : function setup() { createCanvas(windowWidth,windowHeight);
Si el usuario estira o encoge la ventana del navegador, el lienzo se adaptara al tamaño de la ventana en tiempo real.

- Paso 3.CREAR LA ESTRUCTURA DEL ESTADO (function draw)
  3. 3. Aquí usamos un switch Dependiendo del valor de la variable estado, el programa dibujará una cosa u otra.
Usar Valores Relativos
Usaremos fracciones y proporciones
- Cenro del lienzo (width/ 2, height / 2)
- A un cuarto de la pantalla en eje x: (width * 0.25)

- Paso 4.PROGRAMAR VISUALMENTE CADA ESTADO (funciones propias)
4. Ahora creamos las funciones que inventamos en el pasoanterior. Cada una tendrá un diseño y un color diferente
para que se note el cambio.
Incluir un Factor de referencia - referencia = min(width, height) le asignamos para que calcule el minimo

- Paso 5.LA LÓGICA DEL CAMBIO Y EL REINICIO
5. Para pasar de un estado a otro y lograr que vuelva al comienzo,usamos la función mousePressed() Cada vez que
hagas un clic, la variable aumentará. Si llega a 3 (después del estado 2), volverá a 0.
Usar transalte - Push y pop

# De un estado a otro  
1. Interacción con el Teclado
1.1 Por barra espaciadora o Enter:
 ```javascript
function keyPressed() {
  if (key === ' ' || keyCode === ENTER) { // ' ' es el espacio
    estado = estado + 1;
    if (estado > 2) estado = 0;
  }
}
1.2 Por barra espaciadora o Enter:  
 ```javascript
function keyPressed() {
  if (key === '1') estado = 0;
  if (key === '2') estado = 1;
  if (key === '3') estado = 2;
}

2. Botones Reales en la Pantalla: En lugar de hacer clic en cualquier parte de la pantalla,puedes crear un botón real HTML usando la librería de p5.js.Esto es mucho más profesionalpara menús.
´´´javascript
let botonSiguiente;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  
  // Creamos el botón y le ponemos texto
  botonSiguiente = createButton('Continuar');
  botonSiguiente.position(150, 350); // Posición en la pantalla
  
  // Cuando se haga clic en ÉSTE botón, se ejecuta la función cambiarEstado
  botonSiguiente.mousePressed(cambiarEstado);
}

3. Zonas de Clic (Botones dibujados con rect o ellipse)
Si no quieres usar botones de HTML y prefieres dibujar tus propios botones con rect(),puedes evaluar si el mouse estaba dentro de esa caja al hacer clic.

´´´javascript
function mousePressed() {
  // tenemos un botón dibujado en X: 100, Y: 50, Ancho: 200, Alto: 50
  if (mouseX > 100 && mouseX < 300 && mouseY > 50 && mouseY < 100) {
    estado = estado + 1;
    if (estado > 2) estado = 0;
  }
}
4. Interacciones Automáticas (Por Tiempo)
Por Tiempo (Temporizador): Ideal para una pantalla de introducción (Splash Screen) que dura 3 segundos y pasa sola al menú.´
´´´javascript
  // LÓGICA DE CAMBIO AUTOMÁTICO PARA CUALQUIER ESTADO:
  // Si el tiempo transcurrido en el estado actual supera los 3 segundos...
  if (tiempoTranscurrido > duracionEstado) {
    estado = estado + 1; // Avanza al siguiente estado

# INTERACCIÓN CON EL MUNDO FÍSICO
- Camara Web
createCapture(VIDEO);
1. Crear la variable para la captura, declarar una variable global que guardará el flujo de video detu cámara web.

2. Inicializar la cámara en el function setup() utilizamos el comando especial createCapture(VIDEO) esto le pedirá permisoal navegador para encender la cámara del computador. También definimos tamaño con captura.size(x,y); y es muy importante agregar captura.hide(); para que esconda el video que HTML pone abajo por default.

3. Dibujar la cámara en el function draw() usamos la función image(). p5.js toma cada cuadro (frame) de la cámara y lo dibuja en el lienzo en
tiempo real.
´´´javascript
let captura;
function setup() {
  createCanvas(640, 480);
  
  // Capturamos la cámara del computador
  captura = createCapture(VIDEO); 
  captura.size(500, 480); //define tamaño de la captura de video
  captura.hide(); // Esconde el duplicado de HTML
  textAlign(CENTER);
}

function draw() {
  background(0);
  
  // Dibujamos la captura en la posición (0,0)
  image(captura, 0, 0, width, height);
}

- existen efectos como: ON/OFF, Filtros, Loadpixels, pincel de pixeles, pixeles que reaccionan al volumen del computador...


