`translate()` sposta lo schermo in una posizione diversa in base alle coordinate. Le forme sullo schermo si sposteranno con esso ma il loro aspetto non cambierà. Una traslazione può spostare lo schermo in orizzontale, verticale o diagonale.

Questo esempio sposta lo schermo di `50` a destra e di `50` in alto dopo aver disegnato ogni `rect`.

--- code ---
---
language: python
---

def disegna(): rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100)

--- /code ---

![Immagine di un quadrato originale e di due quadrati traslati. Ogni traslazione ha spostato il quadrato a destra di <code>50</code> e in basso di <code>50</code>](images/translate_square.png)

Questo esempio sposta lo schermo di `50` a sinistra e di `50` verso il basso dopo aver disegnato ogni `ellipse`.

--- code ---
---
language: python
---

def disegna(): ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Immagine di un cerchio originale e di due cerchi traslati. Ogni traslazione spostava il quadrato a destra di <code>50</code> e in basso di <code>50</code>](images/translate_circle.png)

In questo esempio, `translate()` viene utilizzato più volte per disegnare occhi complessi senza duplicare tutto il codice per l'occhio sinistro e l'occhio destro:
+ Innanzitutto, `translate(width/2, height/2)` viene utilizzato per iniziare dal centro dello schermo dove viene disegnata una `ellipse` per la testa
+ Successivamente,  `translate(-100, 0)` sposta lo schermo di `100` a sinistra per posizionare l'`occhio()` sinistro
+ Quindi, `translate(200, 0)` sposta di `200` a destra per posizionare l'`occhio()` destro
+ Infine, `translate(-100, 0)` sposta di `100` a sinistra, di nuovo al centro

![Immagine di una testa circolare con un occhio sinistro e uno destro](images/translate_eyes.png)

--- code ---
---
language: python
---

def disegna(): translate(width/2, height/2)  # Posiziona lo schermo al centro stroke(0, 0, 0) ellipse(0, 0, 300, 300)  # Testa a forma di cerchio

    translate(-100, 0)  # Sposta lo schermo di 100 a sinistra per l'occhio sinistro
    occhio() # disegna un occhio
    
    translate(200, 0)  # Sposta lo schermo di 200 a destra per l'occhio destro
    occhio() # disegna un occhio
    
    translate(-100, 0)  # Sposta lo schermo di 100 a sinistra (torna al centro)

def occhio(): # Colori dell'occhio BLU = color(1, 32, 100) NERO = color(0, 0, 0) BIANCO = color(255, 255, 255)

    # Crea un occhio
    stroke(NERO)
    fill(BIANCO)
    ellipse(0, 0, 150, 150)  # occhio esterno
    no_stroke()
    fill(BLU)  # iride
    ellipse(0, 0, 80, 80)
    fill(NERO)  # pupilla
    ellipse(0, 0, 35, 35)
    fill(BIANCO, 70)
    ellipse(-25, -20, 30, 30)  # riflesso
    ellipse(25, 25, 10, 10)  # riflesso

--- /code ---
