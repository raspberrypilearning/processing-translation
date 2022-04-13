`translate()` moves the screen into a different position based on coordinates. Las formas en la pantalla se moverán con ella pero su apariencia no cambiará. A translation can move the screen horizontally, vertically or diagonally.

This example moves the screen `50` to the right and `50` up after each `rect` is drawn.

--- code ---
---
language: python
---

def draw():

  rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) --- /code ---

![Image of an original square and two translated squares. Cada traslación movió el cuadrado hacia la derecha <code>50</code> y hacia abajo <code>50</code>](images/translate_square.png)

This example moves the screen `50` to the left and `50` down after each `ellipse` is drawn.

--- code ---
---
language: python
---

def draw():

  ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Image of an original circle and two translated circles. Cada traslación movió el cuadrado <code>50</code> hacia la derecha y <code>50</code> hacia abajo](images/translate_circle.png)

In this example, `translate()` is used multiple times to draw complex eyes without duplicating all the code for a left-eye and a right-eye:
+ First, `translate(width/2, height/2)` is used to start from the middle of the screen where an `ellipse` for the head is drawn
+ Next,  `translate(-100, 0)` moves `100` to the left to position the left `eye()`
+ Next, `translate(200, 0)` moves `200` to the right to position the right `eye()`
+ Finally, `translate(-100, 0)` moves `100` to the left, back to the middle

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
