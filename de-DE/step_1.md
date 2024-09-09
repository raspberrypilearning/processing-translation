`translate()` verschiebt den Bildschirm basierend auf den Koordinaten an eine andere Position. Die Formen auf dem Bildschirm bewegen sich mit, aber ihr Aussehen ändert sich nicht. Eine Verschiebung kann den Bildschirm horizontal, vertikal oder diagonal verschieben.

Dieses Beispiel verschiebt den Bildschirm um `50` nach rechts und um `50` nach oben, nachdem alle `rect` (kurz für "rectangle" - Rechteck) gezeichnet worden sind.

--- code ---
---
language: python
---

def draw(): rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100)

--- /code ---

![Bild eines Originalquadrats und zweier verschobener Quadrate. Jede Verschiebung verschob das Quadrat nach rechts um <code>50</code> und nach unten um <code>50</code>](images/translate_square.png)

Dieses Beispiel verschiebt den Bildschirm um `50` nach rechts und um `50` nach oben, nachdem alle `ellipse` gezeichnet worden sind.

--- code ---
---
language: python
---

def draw(): ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Bild eines Originalkreises und zweier verschobener Kreise. Jede Verschiebung verschob das Quadrat nach rechts um <code>50</code> und nach unten um <code>50</code>](images/translate_circle.png)

In diesem Beispiel wird `translate()` mehrmals verwendet, um komplexe Augen zu zeichnen, ohne den gesamten Code für ein linkes und ein rechtes Auge zu duplizieren:
+ Zuerst wird mit `translate(width/2, height/2)` in der Mitte des Bildschirms begonnen, wo eine `ellipse` für den Kopf gezeichnet wird
+ Als nächstes bewegt `translate(-100, 0)` um `100` nach links, um das linke `auge()` zu positionieren
+ Als nächstes bewegt `translate(-200, 0)` um `200` nach rechts, um das rechte `auge()` zu positionieren
+ Schließlich bewegt `translate(-100, 0)` um `100` nach links zurück in die Mitte

![Bild eines runden Kopfes mit einem linken und einem rechten Auge](images/translate_eyes.png)

--- code ---
---
language: python
---

def draw(): translate(width/2, height/2)  # Move screen to the middle stroke(0, 0, 0) ellipse(0, 0, 300, 300)  # Circle shaped head

    translate(-100, 0)  # Move screen 100 left for left eye
    eye() #draw an eye
    
    translate(200, 0)  # Move screen 200 right for right eye
    eye() #draw an eye
    
    translate(-100, 0)  # Move screen 100  left (back to the middle)

def eye(): # Eye colours BLUE = color(1, 32, 100) BLACK = color(0, 0, 0) WHITE = color(255, 255, 255)

    # Create an eye
    stroke(BLACK)
    fill(WHITE)
    ellipse(0, 0, 150, 150)  # eye outside
    no_stroke()
    fill(BLUE)  # iris
    ellipse(0, 0, 80, 80)
    fill(BLACK)  # pupil
    ellipse(0, 0, 35, 35)
    fill(WHITE, 70)
    ellipse(-25, -20, 30, 30)  # catchlight
    ellipse(25, 25, 10, 10)  # catchlight

--- /code ---
