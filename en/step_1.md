`Translate()` moves the screen into a different position based on coordinates. The shapes on the screen will move with it but their appearance will not change. A translation can move the screen horizontally, vertically or diagonally.

This example moves the screen `50` to the right and `50` up after each `rect` is drawn.

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

![Image of an original square and two translated squares. Each translation moved the square right `50` and down `50`](images/translate_square.png)

This example moves the screen `50` to the left and `50` down after each `ellipse` is drawn.

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

![Image of an original circle and two translated circles. Each translation moved the square right `50` and down `50`](images/translate_circle.png)
