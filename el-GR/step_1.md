Η συνάρτηση `translate()` μετακινεί την οθόνη σε διαφορετική θέση με βάση τις συντεταγμένες. Τα σχήματα στην οθόνη θα κινούνται μαζί της αλλά η εμφάνισή τους δεν θα αλλάξει. Μια μεταφορά μπορεί να μετακινήσει την οθόνη οριζόντια, κάθετα ή διαγώνια.

Αυτό το παράδειγμα μετακινεί την οθόνη `50` προς τα δεξιά και `50` προς τα πάνω μετά από κάθε σχεδίαση του `rect`.

--- code ---
---
language: python
---

def draw(): rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100) translate(50,-50) rect(150, 150, 100, 100)

--- /code ---

![Εικόνα ενός αρχικού τετραγώνου και δύο τετραγώνων που μεταφέρονται. Κάθε μεταφορά μετακίνησε το τετράγωνο <code>50</code> προς τα δεξιά και <code>50</code> προς τα κάτω](images/translate_square.png)

Αυτό το παράδειγμα μετακινεί την οθόνη `50` προς τα αριστερά και `50` προς τα κάτω μετά τη σχεδίαση κάθε `ellipse`.

--- code ---
---
language: python
---

def draw(): ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100) translate(-50,50) ellipse(200, 200, 100, 100)

--- /code ---

![Εικόνα ενός αρχικού κύκλου και δύο κύκλων που μεταφέρονται. Κάθε μεταφορά μετακίνησε το τετράγωνο <code>50</code> προς τα δεξιά και <code>50</code> προς τα κάτω](images/translate_circle.png)

Σε αυτό το παράδειγμα, το `translate()` χρησιμοποιείται πολλές φορές για να σχεδιάσει περίπλοκα μάτια χωρίς να αντιγράψει όλο τον κώδικα για ένα αριστερό και ένα δεξί μάτι:
+ Αρχικά, το `translate (width/2, height/2)` χρησιμοποιείται για να ξεκινήσει από το κέντρο της οθόνης όπου σχεδιάζεται μια `ellipse` για το κεφάλι
+ Στη συνέχεια,  το `translate(-100, 0)` μετακινείται `100` προς τα αριστερά για να τοποθετήσει το αριστερό `eye()`
+ Στη συνέχεια, το `translate(200, 0)` μετακινείται `200` προς τα δεξιά για να τοποθετήσει το δεξί `eye()`
+ Τέλος, το `translate(-100, 0)` μετακινείται `100` προς τα αριστερά, πίσω στο κέντρο

![Εικόνα ενός κυκλικού κεφαλιού με αριστερό και δεξί μάτι](images/translate_eyes.png)

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
