`translate()` verplaatst het scherm naar een andere positie op basis van coördinaten. De items op het scherm bewegen mee, maar hun uiterlijk verandert niet. Een translatie kan het scherm horizontaal, verticaal of diagonaal bewegen.

Dit voorbeeld verplaatst het scherm `50` naar rechts en `50` omhoog elke keer nadat een `rect` is getekend.

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

![Afbeelding van het oorspronkelijke vierkant en 2 verplaatste vierkanten. Door elke translatie beweegt het vierkant <code>50</code> naar rechts en <code>50</code> naar beneden](images/translate_square.png)

In dit voorbeeld wordt het scherm `50` naar links en `50` naar beneden verplaatst nadat elke `ellips` is getekend.

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

![Afbeelding van de oorspronkelijke cirkel en twee verplaatste cirkels. Door elke translate beweegt het vierkant <code>50</code> naar rechts en <code>50</code> naar beneden](images/translate_circle.png)

In dit voorbeeld wordt `translate()` meerdere keren gebruikt om complexe ogen te tekenen zonder alle code voor het linker- en het rechteroog te dupliceren:
+ Eerst wordt `translate(width/2, height/2)` gebruikt om te beginnen in het midden van het scherm waar een `ellips` voor het hoofd wordt getekend
+ Vervolgens,  `translate(-100, 0)` beweegt `100` naar links om het linker `oog()` te positioneren
+ Vervolgens `translate(200, 0)` beweegt `200` naar rechts om het rechter `oog()` te positioneren
+ Tenslotte, `translate(-100, 0)` beweegt `100` naar links, terug naar het midden

![Afbeelding van een cirkelvormig hoofd met een linker- en rechteroog](images/translate_eyes.png)

--- code ---
---
language: python
---

def draw():
  
  translate(width/2, height/2) # Scherm naar het midden verplaatsen 
  stroke(0, 0, 0)
  ellipse(0, 0, 300, 300) # Cirkelvormig hoofd
  
  translate(-100, 0) # Verplaats het scherm 100 naar links voor het linkeroog
  oog() #teken een oog
    
  translate(200, 0) # Verplaats het scherm 200 naar rechts voor het rechteroog
  oog() #teken een oog
  
  translate(-100, 0) # Verplaats het scherm 100 naar links (terug naar het midden)

def oog():

# Oogkleuren
  BLAUW = color(1, 32, 100) 
  ZWART = color(0, 0, 0) 
  WIT = color(255, 255, 255)

# Maak een oog
  stroke(ZWART)
  fill(WIT)
  ellipse(0, 0, 150, 150) # buitenkant van het oog
  no_stroke()
  fill(BLAUW) # iris
  ellipse(0, 0, 80, 80)
  fill(ZWART) # pupil
  ellipse(0, 0, 35, 35)
  fill(WIT, 70)
  ellipse(-25, -20, 30, 30) # lichtpunt
  ellipse(25, 25, 10, 10) # lichtpunt

--- /code ---