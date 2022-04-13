`translate()`(trasladar) mueve la pantalla a una posición diferente según las coordenadas. Las formas en la pantalla se moverán con ella pero su apariencia no cambiará. Una traslación puede mover la pantalla horizontal, vertical o diagonalmente.

Este ejemplo mueve la pantalla `50` a la derecha y `50` hacia arriba después de dibujar cada `rect` (recta).

--- code ---
---
language: python
---

def draw():

  rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) --- /code ---

![Imagen de un cuadrado original y dos cuadrados trasladados. Cada traslación movió el cuadrado hacia la derecha <code>50</code> y hacia abajo <code>50</code>](images/translate_square.png)

Este ejemplo mueve la pantalla `50` a la izquierda y `50` hacia abajo después de dibujar cada `ellipse` (elipse).

--- code ---
---
language: python
---

def draw():

  ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Imagen de un círculo original y dos círculos trasladados. Cada traslación movió el cuadrado <code>50</code> hacia la derecha y <code>50</code> hacia abajo](images/translate_circle.png)

En este ejemplo, `translate()` (trasladar) se usa varias veces para dibujar ojos complejos sin duplicar todo el código para un ojo izquierdo y un ojo derecho:
+ Primero, `translate(ancho/2, alto/2)` se usa para comenzar desde el medio de la pantalla donde se dibuja una `ellipse` (elipse) para la cabeza
+ Luego,  `translate(-100, 0)` mueve `100` a la izquierda para colocar el `ojo()` izquierdo
+ Luego, `translate(200, 0)` mueve `200` a la derecha para colocar el `ojo()` derecho
+ Finalmente, `translate(-100, 0)` mueve `100` a la izquierda, de regreso al centro

![Imagen de una cabeza circular con ojo izquierdo y uno derecho](images/translate_eyes.png)

--- code ---
---
language: python
---

def draw():

  translate(width/2, height/2) # Move screen to the middle stroke(0, 0, 0) ellipse(0, 0, 300, 300) # Circle shaped head

  translate(-100, 0) # Move screen 100 left for left eye eye() #draw an eye

  translate(200, 0) # Move screen 200 right for right eye eye() #draw an eye

  translate(-100, 0) # Move screen 100  left (back to the middle)

def eye():

# Colores de ojos
  BLUE = color(1, 32, 100) BLACK = color(0, 0, 0) WHITE = color(255, 255, 255)

# Crea un ojo
  stroke(BLACK) fill(WHITE) ellipse(0, 0, 150, 150) # eye outside no_stroke() fill(BLUE) # iris ellipse(0, 0, 80, 80) fill(BLACK) # pupil ellipse(0, 0, 35, 35) fill(WHITE, 70) ellipse(-25, -20, 30, 30) # catchlight ellipse(25, 25, 10, 10) # catchlight

--- /code ---
