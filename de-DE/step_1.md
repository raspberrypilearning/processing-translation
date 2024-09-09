`translate()` verschiebt den Bildschirm basierend auf den Koordinaten an eine andere Position. Die Formen auf dem Bildschirm bewegen sich mit, aber ihr Aussehen ändert sich nicht. Eine Verschiebung kann den Bildschirm horizontal, vertikal oder diagonal verschieben.

Dieses Beispiel verschiebt den Bildschirm um `50` nach rechts und um `50` nach oben, nachdem alle `rect` (kurz für "rectangle" - Rechteck) gezeichnet worden sind.

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

![Bild eines Originalquadrats und zweier verschobener Quadrate. Jede Verschiebung verschob das Quadrat nach rechts um <code>50</code> und nach unten um <code>50</code>](images/translate_square.png)

Dieses Beispiel verschiebt den Bildschirm um `50` nach rechts und um `50` nach oben, nachdem alle `ellipse` gezeichnet worden sind.

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

def draw():
    translate(width/2, height/2)  # Bildschirm in die Mitte verschieben
    stroke(0, 0, 0)
    ellipse(0, 0, 300, 300)  # Kreisförmiger Kopf
    
    translate(-100, 0)  # Bewege den Bildschirm für das linke Auge um 100 nach links
    auge() # zeichne ein Auge
    
    translate(200, 0)  # Bildschirm für das rechte Auge um 200 nach rechts verschieben
    auge() # zeichne ein Auge
    
    translate(-100, 0)  # Bildschirm um 100 nach links bewegen (zurück zur Mitte)

def auge():
    # Augenfarben
    BLAU = color(1, 32, 100)
    SCHWARZ = color(0, 0, 0)
    WEISS = color(255, 255, 255)
    
    # Erstelle ein Auge
    stroke(SCHWARZ)
    fill(WEISS)
    ellipse(0, 0, 150, 150)  # Auge außen
    no_stroke()
    fill(BLAU)  # Iris
    ellipse(0, 0, 80, 80)
    fill(SCHWARZ)  # Pupille
    ellipse(0, 0, 35, 35)
    fill(WEISS, 70)
    ellipse(-25, -20, 30, 30)  # Lichtfang
    ellipse(25, 25, 10, 10)  # Lichtfang
  
--- /code ---
