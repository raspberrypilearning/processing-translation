`translate()` déplace l'écran dans une position différente en fonction des coordonnées. Les formes sur l'écran bougeront avec lui mais leur apparence ne changera pas. Une translation peut déplacer l'écran horizontalement, verticalement ou en diagonale.

Cet exemple déplace l'écran de `50` vers la droite et de `50` vers le haut après chaque `rect` dessiné.

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

![Image d'un carré original et de deux carrés translatés. Chaque translation a déplacé le carré vers la droite de <code>50</code> et vers le bas de <code>50</code>](images/translate_square.png)

Cet exemple déplace l'écran de `50` vers la gauche et de `50` vers le bas après chaque `ellipse` dessinée.

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

![Image d'un cercle original et de deux cercles translatés. Chaque translation a déplacé le carré vers la droite de <code>50</code> et vers le bas de <code>50</code>](images/translate_circle.png)

Dans cet exemple, `translate()` est utilisé plusieurs fois pour dessiner des yeux complexes sans dupliquer tout le code pour un œil gauche et un œil droit :
+ Tout d'abord, `translate(width/2, height/2)` est utilisé pour commencer à partir du milieu de l'écran où une `ellipse` pour la tête est dessinée
+ Ensuite,  `translate(-100, 0)` déplace de `100` vers la gauche pour positionner l'`eye()` gauche
+ Ensuite, `translate(200, 0)` déplace de `200` vers la droite pour positionner l'`eye()`droit
+ Enfin, `translate(-100, 0)` déplace de `100` vers la gauche, vers le milieu

![Image d'une tête de cercle avec un œil gauche et droit](images/translate_eyes.png)

--- code ---
---
language: python
---

def draw():
  
  translate(width/2, height/2) # Déplacer l'écran vers le milieu 
  stroke(0, 0, 0)
  ellipse(0, 0, 300, 300) # Tête en forme de cercle
  
  translate(-100, 0) # Déplacer l'écran de 100 vers la gauche pour l'œil gauche
  eye() #dessiner un oeil
    
  translate(200, 0) # Déplacer l'écran de 200 vers la droite pour l'œil droit
  eye() #dessiner un oeil
  
  translate(-100, 0) # Déplacer l'écran de 100 vers la gauche (retour au milieu)

def eye():

# Couleurs des yeux
  BLUE = color(1, 32, 100)
  BLACK = color(0, 0, 0)
  WHITE = color(255, 255, 255)
  
# Créer un œil
  stroke(BLACK)
  fill(WHITE)
  ellipse(0, 0, 150, 150) # œil externe
  no_stroke()
  fill(BLUE) # iris
  ellipse(0, 0, 80, 80)
  fill(BLACK) # pupille
  ellipse(0, 0, 35, 35)
  fill(WHITE, 70)
  ellipse(-25, -20, 30, 30) # reflet spéculaire
  ellipse(25, 25, 10, 10) # reflet spéculaire

--- /code ---

