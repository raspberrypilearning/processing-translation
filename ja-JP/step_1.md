`translate()`は、座標に基づいて画面を別の位置に移動します。 画面上の図形はそれに合わせて移動しますが、見た目は変わりません。 一度の平行移動（translate）で画面を水平、垂直、または斜めに移動することができます。

この例では、`rect`（四角形）が描画されたあと、画面を`50`だけ右に、`50`だけ上に移動します。

--- code ---
---
language: python
---

def draw():

  rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) --- /code ---

![元の正方形と2つの平行移動された正方形の画像 各平行移動により、 正方形を右に<code>50</code>下に<code>50</code>移動した](images/translate_square.png)

この例では、`ellipse`（楕円）が描画されたあと、画面を`50`だけ左に、`50`だけ下に移動します。

--- code ---
---
language: python
---

def draw():

  ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![元の円と2つの平行移動された円の画像 各平行移動により、 円を右に<code>50</code>下に<code>50</code>移動した](images/translate_circle.png)

この例では、`translate()`を複数回使用することで、左目と右目を描くためのコードをすべて複製することなしに複雑な目を描画しています。
+ まず、`translate(width/2, height/2)`を使って、頭を描く`ellipse`（楕円）が画面の中央から始まるようにします
+ 次に、`translate(-100, 0)`で`100`だけ左に移動して、左目を描く`eye()`の位置を決めます
+ 次に、`translate(200, 0)`で`200`だけ右に移動して、右目を描く`eye()`の位置を決めます
+ 最後に、`translate(-100, 0)`で`100`だけ左に移動して中央に戻ります

![左と右の目がついた円形の頭の画像](images/translate_eyes.png)

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

# 目の色
  BLUE = color(1, 32, 100) BLACK = color(0, 0, 0) WHITE = color(255, 255, 255)

# 目を作る
  stroke(BLACK) fill(WHITE) ellipse(0, 0, 150, 150) # eye outside no_stroke() fill(BLUE) # iris ellipse(0, 0, 80, 80) fill(BLACK) # pupil ellipse(0, 0, 35, 35) fill(WHITE, 70) ellipse(-25, -20, 30, 30) # catchlight ellipse(25, 25, 10, 10) # catchlight

--- /code ---
