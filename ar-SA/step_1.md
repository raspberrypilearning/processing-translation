`translate()`حرك الشاشه في اماكن مختلفه حسب التنسيق. ستتحرك الأشكال التي تظهر على الشاشة معها ولكن مظهرها لن يتغير. يمكن أن تحرك الترجمة الشاشة أفقيًا أو رأسيًا أو قطريًا.

يقوم هذا المثال بتحريك الشاشة `50` إلى اليمين و `50` لأعلى بعد كل `rect` يتم رسمها.

--- code ---
---
language: python
---

def draw(): rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100)

--- /code ---

![صورة لمربع أصلي ومربعين مترجمين. حركت كل ترجمة المربع لليمين <code>50</code> ولأسفل <code>50</code>](images/translate_square.png)

يقوم هذا المثال بتحريك الشاشة `50` إلى اليسار و `50` لأسفل بعد كل `ellipse` يتم رسمه.

--- code ---
---
language: python
---

def draw(): ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![صورة لدائرة أصلية ودائرتين مترجمتين. حركت كل ترجمة المربع لليمين <code>50</code> ولأسفل <code>50</code>](images/translate_circle.png)

في هذا المثال ، يتم استخدام `translate ()` عدة مرات لرسم عيون معقدة دون تكرار كل التعليمات البرمجية للعين اليسرى والعين اليمنى:
+ أولاً ، `translate(width/2, height/2)` يُستخدم للبدء من منتصف الشاشة حيث يتم رسم `ellipse` للرأس
+ بعد ذلك، الايعاز `translate(-100, 0)` يحرك `100` الى اليسار لضبط موقع العين `eye()` اليسرى
+ بعد ذلك، الايعاز `translate(200, 0)` يحرك `200` الى اليمين لضبط موقع العين `eye()` اليمنى
+ أخيرًا ، `translate(-100, 0)` يحرك `100` إلى اليسار، ويعود إلى المنتصف

![صورة رأس دائرة بالعين اليسرى واليمنى](images/translate_eyes.png)

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
