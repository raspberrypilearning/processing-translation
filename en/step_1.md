`Translate()` moves a shape (or group of shapes) into a different position based on coordinates but does not change the appearance. A translation can move something horizontally, vertically or diagonally.

--- code ---
---
language: python
---

--- /code ---
def draw():

  rect(150, 150, 100, 100)
  translate(50,50)
  rect(150, 150, 100, 100)
  translate(50,50)
  rect(150, 150, 100, 100)

![Image of an original square and two translated squares. Each translation moved the square right `50` and down `50`](images/translate_square.png)

--- /collapse ---

--- code ---
---
language: python
---

--- /code ---
def draw():

  ellipse(150, 150, 100, 100)
  translate(50,50)
  ellipse(150, 150, 100, 100)
  translate(50,50)
  ellipse(150, 150, 100, 100)

![Image of an original circle and two translated circles. Each translation moved the square right `50` and down `50`](images/translate_circle.png)
