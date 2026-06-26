# Repo Exámen

---

# *Información del Proyecto*

## *Nombre del proyecto*  
Desigualdad de Género en la Política Chilena

## *Autores*  
Benjamin Ávila y Sara Graadt

---

# *Descripción Objetiva*

### "regla del sistema":
Dos personajes tienen el mismo objetivo (llegar al poder), pero el algoritmo no les entrega las mismas condiciones para alcanzarlo. La desigualdad no está representada por el resultado final, sino por las reglas de interacción que gobiernan el sistema.

## *¿Qué es el proyecto?*

Es una visualización interactiva desarrollada en p5.js que representa de forma visual y dinámica la desigualdad de género en el acceso al poder político en Chile.

 En lugar de representar datos estadísticos de forma convencional, el proyecto transforma la información y el concepto de desigualdad en una experiencia interactiva. El usuario participa activamente manipulando a ambos personajes y observando cómo las reglas del sistema generan comportamientos diferentes para cada uno, haciendo evidente la desigualdad de oportunidades. 

Nuestro  proyecto busca evidenciar lo difícil y arduo que es para el género femenino llegar a cargos políticos en Chile, mostrando al mismo tiempo cómo los hombres logran llegar mucho más rápido al poder, representado de manera explícita una manera clara la desigualdad de género presente en instituciones políticas como lo son el Senado, la Cámara de Diputadas y Diputados, las alcaldías del país, hasta la mismísima presidencia.


---

## *¿Qué se ve en pantalla?*

El proyecto está dividido en tres momentos de navegación.

La primera pantalla corresponde al inicio del proyecto, donde se presenta el título y un botón que permite acceder a la experiencia.

La segunda pantalla entrega las instrucciones necesarias para comprender la interacción, explicando cómo se controla cada personaje y cómo funciona el indicador de presión social.

Finalmente, la tercera pantalla corresponde a la simulación principal. En ella aparecen dos personajes que representan a un hombre y una mujer intentando ascender dentro del sistema político. Ambos se desplazan verticalmente, pero utilizando mecanismos completamente distintos, generando una comparación inmediata entre sus posibilidades de alcanzar el poder.

A medida que ambos avanzan, el fondo cambia progresivamente desde el Congreso Nacional hacia el Palacio de La Moneda, simbolizando el recorrido político desde los espacios legislativos hasta el máximo nivel del poder ejecutivo.

---

## *¿Qué elementos visuales aparecen?*

La composición visual está construida mediante elementos simples que funcionan como símbolos.

Entre ellos aparecen:

- Un personaje masculino vestido formalmente que utiliza un jetpack para ascender rápidamente.
- Un personaje femenino vestida con traje ejecutivo que asciende únicamente mediante una escalera.
- Una escalera vertical que representa el esfuerzo constante y progresivo.
- Un jetpack que simboliza los privilegios o ventajas estructurales.
- Una transición entre imágenes del Congreso Nacional y el Palacio de La Moneda.
- Nubes en movimiento que aportan profundidad y dinamismo al escenario.
- Un indicador porcentual de presión social controlado por el movimiento horizontal del mouse.
- Botones de navegación, reinicio e instrucciones.
  
Cada uno de estos elementos tiene una función dentro del sistema y contribuye a construir la metáfora visual de la desigualdad.


-----

# *Descripción Conceptual*

## *Idea central del proyecto*

La idea principal del proyecto consiste en representar que el acceso al poder político no ocurre bajo las mismas condiciones para todas las personas.

Mientras históricamente los hombres han ocupado la mayor parte de los cargos de representación política y han contado con estructuras que favorecen su participación, las mujeres han debido enfrentar múltiples barreras sociales, culturales e institucionales para alcanzar esos mismos espacios.

Esta diferencia se traduce en el sistema mediante dos formas completamente distintas de movimiento.

El hombre posee un jetpack que le permite ascender continuamente mientras el usuario mantiene presionado el mouse o la barra espaciadora. Su progreso es rápido, fluido y prácticamente sin obstáculos.

La mujer, en cambio, solo puede subir un peldaño cada vez mediante acciones individuales del usuario. Cada avance requiere un esfuerzo adicional, representando el camino más complejo que históricamente han debido recorrer muchas mujeres para acceder a posiciones de liderazgo político.

De esta forma, el algoritmo deja de ser solamente una secuencia de instrucciones y pasa a transformarse en una representación simbólica de una realidad social.


---

## *Regla de oro del sistema*

La lógica principal puede resumirse en la siguiente regla:

> “Mientras más privilegios estructurales posee un personaje, más fácil y rápido resulta su ascenso hacia el poder.”

Esta regla se implementa mediante distintas operaciones del programa.

El hombre posee un movimiento continuo, mientras que la mujer solamente puede avanzar en intervalos fijos de un peldaño.

Además, existe una segunda regla visual:

> “A mayor progreso de los personajes, el escenario transiciona desde el Congreso Nacional hacia el Palacio de La Moneda.”

Esta transformación convierte el espacio político en una representación visual del recorrido hacia las posiciones de mayor poder dentro del Estado chileno.

---

## *¿Cómo se relaciona esta lógica con la problemática de género?*

La desigualdad de género no se representa mediante cifras o gráficos estadísticos, sino mediante diferencias en las reglas del propio sistema.

Los dos personajes persiguen exactamente el mismo objetivo: ascender.

Sin embargo, el programa no les entrega las mismas posibilidades para lograrlo.

Mientras uno puede avanzar constantemente con un solo gesto, la otra necesita repetir una acción varias veces para obtener un progreso equivalente.

Esta diferencia busca representar las barreras estructurales presentes en la política chilena, donde históricamente las mujeres han enfrentado mayores dificultades para acceder a cargos de representación, liderazgo y toma de decisiones.

Así, el código se convierte en una metáfora computacional de la desigualdad.


---

# *Input / Output y Sistema*

## *¿Qué datos entran? (INPUT)*

El sistema recibe información en tiempo real proveniente de la interacción del usuario y de variables internas del programa.

#### Interacción del usuario

- Clic del mouse (mousePressed)
- Posición horizontal del mouse (mouseX)
- Barra espaciadora (SPACE)
- Flecha hacia arriba (UP_ARROW)
- Flecha hacia abajo (DOWN_ARROW)
-Variables del sistema
- Estado de la aplicación (estado)
- Posición vertical del hombre (hombreY)
- Posición vertical de la mujer (mujerY)
- Estado del jetpack (jetpackFuego)
- Posición y velocidad de las nubes
- Tamaño de la ventana (windowWidth y windowHeight)


### *Datos utilizados*

| Elemento  | Representación |
|---|---|
| Congreso Nacional |Inicio del recorrido político y espacio legislativo.
| Palacio de La Moneda | Meta del ascenso y representación del máximo poder ejecutivo. |
| Hombre | Representa los privilegios históricos masculinos para acceder al poder político. |
| Mujer | Representa el mayor esfuerzo requerido para alcanzar espacios de representación política. |
| Escalera | Simboliza las barreras estructurales y el ascenso progresivo. |
| Jetpack | Simboliza las ventajas y facilidades históricas asociadas al género masculino. |

#### Referencias conceptuales
- Participación histórica de mujeres en la política chilena.
- Congreso Nacional de Chile.
- Palacio de La Moneda.
- Estudios sobre desigualdad de género y representación política.

---

## *¿Cómo se procesan y transforman?*

El programa transforma constantemente los datos ingresados mediante diversas funciones y reglas computacionales.

| Función | Transformación |
| --- | --- |
| mousePressed() | Cambia de pantalla, reinicia el sistema o hace avanzar a la mujer. |
| keyPressed() | Permite subir o bajar a la mujer exactamente un peldaño. |
| map() | Convierte la posición del mouse en un porcentaje de presión social. |
| map() | Calcula la transición entre Congreso y La Moneda según el progreso de ambos personajes. |
| constrain() | Limita el movimiento de ambos personajes dentro del escenario. |
| random() | Genera posiciones, tamaños y velocidades distintas para las nubes y el fuego del jetpack. |
| if | Determina qué pantalla mostrar y cómo responde cada personaje según la interacción del usuario. |


---

## *¿Qué respuesta visual producen? (OUTPUT)*

- Ascenso continuo del hombre mediante el jetpack.
- Ascenso escalonado de la mujer utilizando la escalera.
- Activación y animación del fuego del jetpack.
- Movimiento continuo de las nubes.
- Aparición progresiva del Palacio de La Moneda.
- Desaparición gradual del Congreso Nacional.
- Desplazamiento del fondo simulando avance hacia el poder.
- Actualización en tiempo real del indicador de presión social.
- Cambio entre pantallas (Inicio, Instrucciones e Interacción).
- Reinicio completo de la simulación.

---

# *Pensamiento Computacional*

## *Reglas que gobiernan el sistema*

| Elemento | Regla computacional |
| --- | --- |
| Hombre | Asciende continuamente mientras se mantiene presionado el mouse o la barra espaciadora. |
| Mujer | Solo avanza un peldaño (60 px) por cada acción del usuario. |
| Jetpack | Solo aparece cuando el hombre está ascendiendo. |
| Fondo | La opacidad del Congreso disminuye mientras aumenta la de La Moneda según el progreso promedio. |
| Nubes | Se desplazan constantemente hacia la izquierda y reaparecen al salir de pantalla. |
| Movimiento | constrain() impide que los personajes abandonen los límites del escenario. |
| Estados | La interfaz cambia entre Inicio, Instrucciones e Interacción mediante la variable estado. |

---

## *Explicación del sistema de interactividad*

La interacción está diseñada para que el usuario experimente directamente una desigualdad en las posibilidades de ascenso.

El personaje masculino responde a una interacción continua: basta con mantener presionado el mouse o la barra espaciadora para que ascienda de forma constante gracias al jetpack. Esta mecánica representa un acceso más directo y privilegiado hacia el poder político.

En contraste, el personaje femenino requiere una acción individual para avanzar cada peldaño de la escalera. Cada pulsación de la flecha superior o cada clic en la zona de la escalera produce un único avance, obligando al usuario a realizar un esfuerzo repetitivo para alcanzar la misma altura.

Finalmente, el progreso conjunto de ambos personajes modifica el escenario mediante una transición gradual entre el Congreso Nacional y el Palacio de La Moneda. De esta forma, el entorno también responde a la interacción del usuario, reforzando visualmente la idea de acercarse a los espacios de mayor poder político.


# *Referentes*

## *Referentes Visuales*

### *Barbara Kruger*
Artista visual feminista reconocida por utilizar tipografía, fotografía y mensajes políticos directos para cuestionar las estructuras de poder, el género y los medios de comunicación. Inspiró el uso de un contraste visual dentro del proyecto.

### Guerrilla Girls
Colectivo feminista de artistas fundado en 1985 que denuncia la desigualdad de género mediante afiches, estadísticas, humor y visualización de datos.

### *Lotty Rosenfeld*
Artista chilena perteneciente a la Escena de Avanzada. Utilizó intervenciones urbanas y símbolos visuales para cuestionar el poder político y las estructuras patriarcales en Chile durante la dictadura. Referente por el uso del espacio visual como denuncia política.

---

## *Referentes Teóricos*

### *Feminism for the 99%*  
Texto sobre desigualdad estructural de género en sistemas políticos y económicos.

### *Simone de Beauvoir*
Autora de “El segundo sexo”, obra fundamental para comprender la desigualdad histórica entre hombres y mujeres y la exclusión femenina en espacios de poder.

### Comisión Económica para América Latina y el Caribe
Organismo de Naciones Unidas que publica investigaciones sobre igualdad de género y participación política en América Latina.

### Ministerio de la Mujer y la Equidad de Género
Institución pública encargada de promover la igualdad entre hombres y mujeres en Chile.

---

## *Referentes Históricos*

### *Sufragio femenino en Chile (1949)*  
Contexto histórico fundamental para comprender la representación política femenina en Chile.

### Ley de Cuotas Electorales (2015)
Estableció un porcentaje mínimo de candidaturas femeninas para promover una mayor representación de mujeres en el Congreso.

## *Sufragistas chilenas*
Movimiento feminista que logró el derecho a voto femenino en elecciones presidenciales en Chile en 1949. Referente histórico clave para contextualizar la baja representación política femenina actual.

### *Revuelta feminista chilena de 2018*
Movimiento estudiantil y social que visibilizó masivamente desigualdades estructurales de género en Chile, utilizando performance, gráfica y activismo visual como herramientas de protesta. 

### Convención Constitucional (2021)
Fue el primer órgano constituyente del mundo elegido con paridad de género.
---
  # *Diagrama de Flujo en markDown*
<img width="2641" height="6059" alt="diagrama de flujo" src="https://github.com/user-attachments/assets/ca16793d-bbdd-4539-9c14-1a11e36ed260" />

# *Link al sketch en p5.js en formato editable*  
https://editor.p5js.org/saragraadt/sketches/jv2S_lxvP

---
# *Codigo de p5.js*  
```javascript
// Variables 
let estado = "INICIO";
let mujerY; // Posición vertical (Y) de la mujer
let hombreY; // Posición vertical (Y) del hombre
let jetpackFuego = false; // Controla si se dibuja el fuego del jetpack


//Para las nubes
class ElementoNube {
  constructor() {
    this.x = random(width); // Asigna una posición X aleatoria dentro del ancho del lienzo
    this.y = random(100, height - 200); // Asigna una posición Y aleatoria en un rango vertical
    this.speed = random(0.2, 0.5); // Define una velocidad de movimiento aleatoria y suave
    this.size = random(60, 100); // Define un tamaño aleatorio para la nube
  }

  actualizar() {
    this.x -= this.speed; // Mueve la nube hacia la izquierda restando velocidad en X
    if (this.x < -100) {
      // Si la nube se sale por completo del borde izquierdo
      this.x = width + 100; //la reubica al extremo derecho para reaparecer
      this.y = random(100, height - 200); //Le asigna una nueva altura aleatoria
    }
  }
}
//Variables fondo
let nubes = []; // Crea el arreglo vacío para almacenar las nubes
let imgFondoCongreso; // Variable para guardar la imagen del Congreso Nacional
let imgFondoMoneda; // Variable para guardar la imagen de La Moneda

// Paleta de colores
let colorFondo = [26, 122, 146]; // Azul para el fondo de las
let colorEscalera = [230, 57, 70]; // Rojo para la escalera y elementos de alerta
let colorTraje = [29, 53, 87]; // Azul oscuro para la ropa formal y botones
let colorCamisa = [255]; // Blanco para camisas y textos 

//Carga de las imagenes de fondo
function preload() {
  imgFondoCongreso = loadImage("assets/congreso.png"); //Carga el archivo del Congreso
  imgFondoMoneda = loadImage("assets/moneda.png"); // Carga el archivo de La Moneda
}

//Configuración inicial
function setup() {
  createCanvas(1920, 1080); // Crea el lienzo de dibujo con tamaño fijo
  angleMode(DEGREES);// cambia el sistema de unidades utilizado para medir ángulos
  windowResized(); //función para adaptar el tamaño a la ventana si esta es manipulada
  resetVariablesAgentes(); // Ejecuta la función que pone a los personajes en su posición inicial

//Loop para las nubes
  for (let i = 0; i < 5; i++) {
    // Bucle que corre 5 veces para las nubes
    nubes.push(new ElementoNube()); // Crea una nueva nube y la mete dentro del arreglo 'nubes'
  }
}
// Creación de 3 pantallas
function draw() {
  background(colorFondo); // Pinta el fondo general
  //para cambiar las pantallas
  if (estado === "INICIO") {
    // Si el estado actual es igual a "INICIO"
    pantallaInicio(); // Ejecuta y dibuja la pantalla de presentación
  } else if (estado === "INSTRUCCIONES") {
    // Si el estado es igual a "INSTRUCCIONES"
    pantallaInstrucciones(); // Ejecuta y dibuja la pantalla con las reglas
  } else {
    // Si no es ninguna de las anteriores (es INTERACCION)
    pantallaInteraccion(); // Ejecuta el simulador principal
  }
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight); //Redimensiona el lienzo al ancho y alto actual del navegador
}

//REINICIO
function resetVariablesAgentes() {
  mujerY = height - 120; // Posiciona a la mujer cerca del borde inferior del lienzo
  hombreY = height - 150; // Posiciona al hombre un poco más arriba que la mujer
  jetpackFuego = false; // Apaga el estado del fuego del jetpack
}

// Pantalla 1 (pantalla de inicio)
function pantallaInicio() {
  
  background(colorFondo); // Aplica el color azul al fondo
  dibujarNubes(); // Llama a la función que pinta y mueve las nubes de fondo

  textAlign(CENTER, CENTER); // Alinea los textos de manera horizontal y vertical al centro
  fill(255); // Define el color del texto a blanco 
  text("DESIGUALDAD DE GÉNERO EN LA POLÍTICA CHILENA", width / 2, height * 0.4); // Dibuja título

   textSize(16); // Cambia el tamaño de letra a 16px
  fill(230, 57, 70); // Cambia el color del texto a rojo
  text("Examen Final - Pensamiento Computacional UDP", width / 2, height * 0.55  ); // Dibuja el subtítulo

  rectMode(CENTER); // Configura los rectángulos para dibujarse desde su centro exacto
  fill(colorTraje); // Activa el color azul oscuro para el botón
  rect(width / 2, height * 0.68, 200, 50, 10); // Dibuja la forma del botón con esquinas redondeadas (10px)
  fill(255); // Cambia el color a blanco para las letras del botón
  text("INGRESAR", width / 2, height * 0.68); // Escribe el texto centrado arriba del botón
}
// Pantalla 2 ( Instrucciones)
function pantallaInstrucciones() {
  background(colorFondo); // Pinta el fondo del color base
  dibujarNubes(); // Dibuja las nubes en segundo plano

  rectMode(CENTER); // Asegura el dibujo desde el centro para el cuadro contenedor
  fill(29, 53, 87, 230); // Aplica azul oscuro con transparencia (230 de 255)
  strokeWeight(2); // Define el grosor del borde en 2 píxeles
  rect(width / 2, height / 2, min(width * 0.75, 650), min(height * 0.6, 420),10); // Dibuja el recuadro contenedor

  textAlign(CENTER, CENTER); // Centra el texto de instrucciones
  noStroke(); // Desactiva el borde para que el texto 
  fill(255); // Color blanco para el texto
  textSize(22); // Tamaño de título para las reglas
  text("REGLAS DEL MODELO COMPUTACIONAL", width / 2, height * 0.26); // Escribe el encabezado

  textAlign(LEFT, TOP); // Cambia alineación a la izquierda y arriba para el bloque largo de texto
  textSize(14); // Tamaño de lectura cómodo
  let textoInstrucciones = // Variable temporal que une las líneas de texto de la guía
    "• Dinámica del Candidato: Sube de manera fluida y continua\n" +
    "  manteniendo presionado el MOUSE o la BARRA ESPACIADORA.\n\n" +
    "• Dinámica de la Candidata: Sube manualmente peldaño por peldaño\n" +
    "  presionando FLECHA ARRIBA o ABAJO.\n\n";

  text(textoInstrucciones, width / 2 - min(width * 0.33, 290), height * 0.36); // Renderiza el bloque de texto formateado

  textAlign(CENTER, CENTER); // Vuelve a centrar para el diseño del botón
  fill(colorEscalera); // Aplica color rojo al botón de inicio
  rect(width / 2, height * 0.76, 220, 45, 8); // Dibuja el botón de inicio
  fill(255); // Texto blanco
  text("INICIAR SIMULACIÓN", width / 2, height * 0.76); // Escribe el texto sobre el botón rojo
}

// Pantalla 3( Interaccion)
function pantallaInteraccion() {
  rectMode(CORNER); // Reinicia el modo de dibujo de rectángulos a la esquina
  background(colorFondo); // Establece el color de fondo base

  //variacion posicion personas
  let alturaHombreProporcional = height - 150 - hombreY; // Calcula cuánto ha subido el hombre desde su base
  let alturaMujerProporcional = height - 120 - mujerY; // Calcula cuánto ha subido la mujer desde su base
  
  // Se calcula el promedio internamente para controlar los fondos
  let promedioProgreso = (alturaHombreProporcional + alturaMujerProporcional) / 2; 

  //Fondo imagenes segun desplazamiento
  let desplazamientoY = map(promedioProgreso, 0, height, 0, 150); // Mapea el progreso para mover el fondo

  let opacidadMoneda = map(promedioProgreso, 0, height - 200, 0, 75); // Mapea la opacidad de La Moneda

  let opacidadCongreso = 50 - map(promedioProgreso, 0, height - 200, 0, 50); // Reduce la opacidad del Congreso
  opacidadCongreso = constrain(opacidadCongreso, 0, 50); 

  if (opacidadCongreso > 0) {
    tint(255, opacidadCongreso); 
    image(imgFondoCongreso, 0, desplazamientoY, width, height); 
  }

  if (opacidadMoneda > 0) {
    tint(255, opacidadMoneda); 
    image(imgFondoMoneda, 0, desplazamientoY - 40, width, height); 
  }
  noTint(); 

  dibujarNubes(); 
  dibujarEscalera(); 

  //interaccion con usuario
  if (mouseIsPressed || (keyIsPressed && key === " ")) {
    hombreY -= 3; 
    jetpackFuego = true; 
  } else {
    if (hombreY < height - 150) {
      hombreY += 1.5; 
    }
    jetpackFuego = false; 
  }

  dibujarHombre(width * 0.3, hombreY); 

  mujerY = constrain(mujerY, 80, height - 120); 
  dibujarMujer(width * 0.75, mujerY); 

  mostrarInstrucciones(); 

  fill(colorEscalera); // Activa el rojo para el botón de reseteo
  rect(width - 665, 380, 130, 35, 6); // Dibuja el botón de RESET arriba a la derecha
  fill(255); // Texto blanco
  textAlign(CENTER, CENTER); // Centra el texto en el botón
  text("REINICIAR (RESET)", width - 600, 400); //Escribe la etiqueta del botón
}

// COMPONENTES VISUALES
// Dibulo escalera
function dibujarEscalera() {
  let posX = width * 0.75; // Define el centro de la escalera alineado con la mujer
  stroke(colorEscalera); // Usa el color rojo para los pasamanos de la escalera
  strokeWeight(12); // Establece vigas laterales gruesas de 12px
  line(posX - 30, 0, posX - 30, height); // Dibuja la barra vertical izquierda de la escalera
  line(posX + 30, 0, posX + 30, height); // Dibuja la barra vertical derecha de la escalera

  strokeWeight(8); // Reduce el grosor a 8px para los peldaños horizontales
  for (let y = 0; y < height; y += 60) {
    // Bucle que genera peldaños cada 60 píxeles de arriba a abajo
    line(posX - 30, y, posX + 30, y); // Dibuja cada peldaño uniendo los dos pasamanos
  }
}
// Dibujo Hombre
function dibujarHombre(x, y) {
  push(); // Aísla el sistema de coordenadas para no alterar otros dibujos
  translate(x, y); // Mueve el origen (0,0) al punto exacto donde debe estar el hombre
  noStroke(); // Quita los contornos en las formas del personaje

  fill(colorEscalera); // Color rojo para el tanque del Jetpack
  rect(-25, 10, 20, 60, 5); // Dibuja el propulsor en la espalda del personaje

  if (jetpackFuego) {
    // Si el fuego está encendido
    fill(255, 150, 0, 200); // Naranja con ligera transparencia para la llama externa
    triangle(-20, 70, -10, 70, -15, 95 + random(0, 15)); // Dibuja llama grande con parpadeo aleatorio
    fill(255, 230, 0); // Amarillo brillante para el núcleo caliente de la llama
    triangle(-18, 70, -12, 70, -15, 85 + random(0, 10)); // Llama interna con parpadeo más corto
  }

  fill(colorTraje); // Azul oscuro para el cuerpo
  rect(-10, 0, 30, 80, 4); // Torso del personaje
  rect(-8, 80, 12, 60); // Pierna izquierda
  rect(6, 80, 12, 60); // Pierna derecha

  fill(colorCamisa); // Blanco para el cuello de la camisa
  triangle(-2, 0, 12, 0, 5, 25); // Triángulo invertido que simula la apertura 
  fill(colorEscalera); // Rojo para la corbata
  quad(1, 1, 7, 1, 8, 20, 5, 25); // Forma rectangular para corbata

  fill(255); // Color cabeza
  ellipse(5, -15, 25, 25); // Cabeza del personaje

  fill(0); // Negro para el pelo
  arc(5, -20, 28, 20, 180, 360); // Medio círculo superior que simula el pelo

  pop(); // Restaura la matriz de dibujo previa
}

// Dibujo Mujer
function dibujarMujer(x, y) {
  push(); // Guarda el estado actual del lienzo
  translate(x, y); // Mueve el punto de origen a las coordenadas de la mujer
  noStroke(); // Desactiva bordes

  fill(255); // Color blanco para las piernas
  rect(-12, 55, 10, 60); // Pierna izquierda
  rect(4, 50, 10, 40); // Pierna derecha (un poco desfasada simulando paso o escala)

  fill(colorTraje); // Azul oscuro para la ropa
  rect(-15, 0, 30, 40, 4); // Torso
  quad(-15, 40, 15, 40, 18, 60, -18, 60); // Falda 

  fill(255); // Cabeza blanca
  ellipse(0, -15, 24, 24); // cabeza forma circular
  fill(0); // Color negro para el pelo
  ellipse(5, -15, 26, 26); // forma del pelo
 
  stroke(colorTraje); // color de la misma ropa
  strokeWeight(8); // Grosor del brazo levantado
  line(5, 10, 25, -20); // Brazo estirado hacia arriba como si estuviera sujetando el peldaño

  pop(); // Restaura el lienzo
}

//Dibujo Nubes
function dibujarNubes() {
  fill(255, 255, 255, 180); // Blanco con opacidad semi-transparente para las nubes 
  noStroke(); // Sin contornos
  for (let nube of nubes) {
    // Recorrido
    ellipse(nube.x, nube.y, nube.size, nube.size * 0.6); // Froma de esfera para la nube 
    ellipse(nube.x + 20, nube.y + 10, nube.size * 0.8, nube.size * 0.5); // Esfera secundaria de nube

    nube.actualizar(); // Invoca el método interno de la clase para que la nube se mueva sola
  }
}

//Texto
function mostrarInstrucciones() {
  fill(255); // Texto blanco plano
  noStroke(); // Sin contorno
  textSize(14); // Tamaño 14px
  textAlign(LEFT); // Justificado a la izquierda
  text(" HOMBRE (Jetpack): Mantén presionado MOUSE o ESPACIO", 30, 40); // Texto recordatorio del hombre
  text(" MUJER (Escalera): Usa FLECHA ARRIBA / ABAJO", 30, 60 ); // Texto recordatorio de la mujer
}

// INTERACCIONES TECLADO
function keyPressed() {
  if (estado === "INTERACCION") {
    // Se activa unicamente en la pantalla 3 ( interaccion)
    if (keyCode === UP_ARROW) {
      // Si la tecla presionada es la Flecha Arriba
      mujerY -= 60; // Sube a la mujer exactamente un peldaño (60px)
    } else if (keyCode === DOWN_ARROW) {
      // Si la tecla es la Flecha Abajo
      mujerY += 60; // Baja a la mujer un peldaño (60px)
    }
  }
}

// --- INTERACCIONES POR MOUSE ---
function mousePressed() {
  if (estado === "INICIO") {
    if (
      mouseX > width / 2 - 100 &&
      mouseX < width / 2 + 100 &&
      mouseY > height * 0.65 &&
      mouseY < height * 0.65 + 50
    ) {
      estado = "INSTRUCCIONES";
    }
  } else if (estado === "INSTRUCCIONES") {
    if (
      mouseX > width / 2 - 110 &&
      mouseX < width / 2 + 110 &&
      mouseY > height * 0.75 &&
      mouseY < height * 0.75 + 45
    ) {
      estado = "INTERACCION";
    }
  } else if (estado === "INTERACCION") {
    if (
      mouseX > width - 665 &&
      mouseX < (width - 665) + 130 &&
      mouseY > 380 &&
      mouseY < 380 + 35
    ) {
      resetVariablesAgentes(); // Resetea posiciones
      estado = "INICIO"; // Vuelve a la pantalla principal
    }
  }
}




