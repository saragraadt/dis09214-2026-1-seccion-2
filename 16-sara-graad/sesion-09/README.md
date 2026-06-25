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

# Subir Imagen
Cargar la imagen con preload
  
