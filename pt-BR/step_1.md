O `translate()` move a tela para uma posição diferente baseado nas coordenadas. As formas na tela serão movidas com ele, mas a aparência delas não mudará. Uma translação pode mover a tela na horizontal, vertical ou diagonal.

Este exemplo move a tela `50` para a direta e `50` para cima depois que cada `rect` é desenhado.

--- code ---
---
language: python
---

def draw():

  rect(150, 150, 100, 100)
  translate(50,-50)
  rect(150, 150, 100, 100)
  translate(50,-50)
  rect(150, 150, 100, 100)
--- /code ---

![Imagem de um quadrado original e dois quadrados deslocados. Cada translação moveu o quadrado <code>50</code> para a esquerda e <code>50</code> para baixo](images/translate_square.png)

Esse exemplo move a tela `50` para a esquerda `50` para baixo depois que cada `ellipse` é desenhada.

--- code ---
---
language: python
---

def draw():

  ellipse(200, 200, 100, 100) 
  translate(-50,50) 
  ellipse(200, 200, 100, 100) 
  translate(-50,50) 
  ellipse(200, 200, 100, 100)

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

  translate(width/2, height/2) #  Move a tela para o meio 
  stroke(0, 0, 0) 
  ellipse(0, 0, 300, 300) # Cabeça em forma de círculo

  translate(-100, 0) # Move a tela 100 para a esquerda para o olho esquerdo 
  olho() #desenha um olho

  translate(200, 0) # Move a tela 200 para a direita para o olho direito
  olho() #desenha um olho

  translate(-100, 0) # Move a tela 100 para a esquerda (de volta ao meio)

def olho():

# Cores dos olhos
  AZUL = color(1, 32, 100) 
  PRETO = color(0, 0, 0) 
  BRANCO = color(255, 255, 255)

# Criar um olho
  stroke(PRETO)
  fill(BRANCO)
  ellipse(0, 0, 150, 150) # contorno do olho
  no_stroke()
  fill(AZUL) # íris
  ellipse(0, 0, 80, 80)
  fill(PRETO) # pupila
  ellipse(0, 0, 35, 35)
  fill(BRANCO, 70)
  ellipse(-25, -20, 30, 30) # reflexo da luz
  ellipse(25, 25, 10, 10) # reflexo da luz
  
--- /code ---
