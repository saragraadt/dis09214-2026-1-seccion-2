#Diseño Responsivo (windowResiezed)

Paso 1. crear un canvas con dimensiones dinamicas:(windowWidth, windowHeight)
- function setup() { createCanvas(windowWidth,windowHeight);
Si el usuario estira o encoge la ventana del navegador, el lienzo se adaptara al tamaño de la ventana en tiempo real.

Paso 3. Usar Valores Relativos
Usaremos fracciones y proporciones
- Cenro del lienzo (width/ 2, height / 2)
- A un cuarto de la pantalla en eje x: (width * 0.25)

Paso 4. Incluir un Factor de referencia
- referencia = min(width, height)
le asignamos para que calcule el minimo

Paso 5. Usar transalte - Push y pop


# Subir Imagen
Cargar la imagen con preload
  
