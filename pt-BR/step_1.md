O `translate()` move a tela para uma posição diferente baseado nas coordenadas. As formas na tela serão movidas com ele, mas a aparência delas não mudará. Uma translação pode mover a tela na horizontal, vertical ou diagonal.

Este exemplo move a tela `50` para a direta e `50` para cima depois que cada `rect` é desenhado.

--- code ---
---
language: python
---

def draw():

  rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) --- /code ---

![Imagem de um quadrado original e dois quadrados deslocados. Cada translação moveu o quadrado <code>50</code> para a esquerda e <code>50</code> para baixo](images/translate_square.png)

Esse exemplo move a tela `50` para a esquerda `50` para baixo depois que cada `ellipse` é desenhada.

--- code ---
---
language: python
---

def draw():

  ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Imagem de um círculo original e dois círculos deslocados. Cada translação moveu o quadrado <code>50</code> para a direta e <code>50</code> para baixo](images/translate_circle.png)

Neste exemplo, o `translate()` é usado diversas vezes para desenhar olhos complexos, sem duplicar todo o código para um olho esquerdo e um olho direito:
+ Primeiramente, o `translate(width/2, height/2)` é usado para iniciar no centro da tela, onde uma `ellipse` é desenhada para a cabeça
+ Em seguida, o  `translate(-100, 0)` se move `100` para a esquerda para posicionar o `olho()` esquerdo
+ Depois, o `translate(200, 0)` se move `200` para a direita para posicionar o `olho()` direito
+ Enfim, o `translate(-100, 0)` se move `100` para a esquerda, de volta ao meio

![Imagem de uma cabeça circular com um olho esquerdo e um olho direito](images/translate_eyes.png)

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

# Cores dos olhos
  BLUE = color(1, 32, 100) BLACK = color(0, 0, 0) WHITE = color(255, 255, 255)

# Criar um olho
  stroke(BLACK) fill(WHITE) ellipse(0, 0, 150, 150) # eye outside no_stroke() fill(BLUE) # iris ellipse(0, 0, 80, 80) fill(BLACK) # pupil ellipse(0, 0, 35, 35) fill(WHITE, 70) ellipse(-25, -20, 30, 30) # catchlight ellipse(25, 25, 10, 10) # catchlight

--- /code ---
