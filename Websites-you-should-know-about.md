## 🧱 HTML – das solltest du sicher beherrschen

### Grundstruktur

- `<!DOCTYPE html>`
    
- `<html>`
    
- `<head>`
    
- `<body>`
    
- `<meta>`
    
- `<title>`
    
- `<link>`
    
- `<script>`
    

### Semantische Struktur

Die würde ich wirklich verstehen und nicht nur auswendig kennen:

- `<header>` – Kopfbereich einer Seite oder Section
    
- `<nav>` – Navigation
    
- `<main>` – Hauptinhalt
    
- `<section>` – thematischer Abschnitt
    
- `<article>` – eigenständiger Inhalt
    
- `<aside>` – ergänzender Inhalt
    
- `<footer>` – Fußbereich
    

Zum Beispiel:

```html
<body>
  <header>
    <nav>...</nav>
  </header>

  <main>
    <section class="hero">
      ...
    </section>

    <section class="features">
      ...
    </section>

    <section class="about">
      ...
    </section>
  </main>

  <footer>
    ...
  </footer>
</body>
```

### Inhaltselemente

Die solltest du problemlos einsetzen können:

- `<h1>` – `<h6>`
    
- `<p>`
    
- `<a>`
    
- `<img>`
    
- `<button>`
    
- `<ul>`, `<ol>`, `<li>`
    
- `<strong>`, `<em>`
    
- `<span>`
    
- `<div>`
    

**`div` und `span`** sind wichtig, aber ich würde mir angewöhnen, zuerst zu überlegen:

> Gibt es ein semantisch passenderes HTML-Element?

Also lieber `<nav>` statt `<div class="nav">`.

### Formulare

Für viele Websites relevant:

- `<form>`
    
- `<label>`
    
- `<input>`
    
- `<textarea>`
    
- `<select>`
    
- `<option>`
    
- `<button>`
    

Außerdem:

- `type="email"`
    
- `type="password"`
    
- `type="checkbox"`
    
- `type="radio"`
    
- `type="submit"`
    

### Bilder & Links

Du solltest sicher mit sowas sein:

```html
<a href="/about">Über uns</a>

<img
  src="image.jpg"
  alt="Beschreibung des Bildes"
>
```

Und insbesondere verstehen, warum `alt` wichtig ist.

---

# 🎨 CSS – hier liegt der größte Hebel

Wenn du schöne Websites bauen willst, würde ich CSS ungefähr in dieser Reihenfolge lernen.

## 1. Box Model ⭐⭐⭐⭐⭐

Das ist absolut fundamental:

```css
box-sizing: border-box;

width
height
padding
margin
border
```

Du solltest intuitiv verstehen:

```css
.card {
  width: 300px;
  padding: 20px;
  border: 1px solid;
  margin: 20px;
}
```

und warum sich die tatsächliche Größe daraus ergibt.

Ich würde direkt global:

```css
* {
  box-sizing: border-box;
}
```

verwenden.

---

# 2. Flexbox ⭐⭐⭐⭐⭐

Ja — **unbedingt**.

Das ist wahrscheinlich das wichtigste CSS-Layout-System für den Einstieg.

Du solltest können:

```css
.container {
  display: flex;
}
```

und insbesondere:

```css
flex-direction
justify-content
align-items
gap
flex-wrap
flex
```

Zum Beispiel:

```css
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
}
```

Und diese Konzepte wirklich verstehen:

### Hauptachse

```css
flex-direction: row;
```

vs.

```css
flex-direction: column;
```

### Ausrichtung

```css
justify-content
align-items
```

### Abstand

```css
gap
```

Das reicht schon für unglaublich viele Layouts.

---

# 3. CSS Grid ⭐⭐⭐⭐⭐

Nach Flexbox unbedingt **Grid**.

```css
.cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}
```

Du solltest kennen:

```css
display: grid;

grid-template-columns
grid-template-rows
gap

grid-column
grid-row

repeat()
minmax()
```

Ein sehr wichtiger Pattern:

```css
.cards {
  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(250px, 1fr)
  );
  gap: 2rem;
}
```

Damit kannst du schon sehr schöne responsive Kartenlayouts bauen.

---

# 4. Abstände & Größen ⭐⭐⭐⭐⭐

Sehr wichtig für gutes Design.

Du solltest verstehen:

```css
width
max-width
min-width

height
min-height
max-height

margin
padding
gap
```

Besonders:

```css
max-width: 1200px;
margin: 0 auto;
```

ist ein Klassiker für Landingpages.

---

# 5. Typografie ⭐⭐⭐⭐⭐

Eine Website kann technisch perfekt sein und trotzdem hässlich aussehen, wenn die Typografie schlecht ist.

Können solltest du:

```css
font-family
font-size
font-weight
line-height
letter-spacing
text-align
text-transform
```

Zum Beispiel:

```css
h1 {
  font-size: 4rem;
  line-height: 1.05;
  letter-spacing: -0.04em;
}
```

Und vor allem:

### `rem`

```css
font-size: 1rem;
padding: 2rem;
gap: 1.5rem;
```

Du solltest verstehen, warum man nicht alles in `px` baut.

---

# 6. Farben ⭐⭐⭐⭐

```css
color
background
background-color
border-color
```

und moderne Farben:

```css
color: #111827;
background: #f9fafb;
```

sowie:

```css
rgb()
rgba()
hsl()
```

CSS Variables sind ebenfalls **sehr wichtig**:

```css
:root {
  --primary: #6366f1;
  --background: #0f172a;
  --text: #f8fafc;
  --radius: 12px;
}
```

Dann:

```css
button {
  background: var(--primary);
  border-radius: var(--radius);
}
```

Damit kannst du sehr schnell ein konsistentes Design bauen.

---

# 7. `border`, `border-radius` & Schatten ⭐⭐⭐⭐

Für „hübsche“ Websites extrem relevant:

```css
border
border-radius
box-shadow
```

Zum Beispiel:

```css
.card {
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}
```

---

# 8. Positionierung ⭐⭐⭐⭐

Du solltest verstehen:

```css
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

und:

```css
top
right
bottom
left
z-index
```

Besonders wichtig ist die Kombination:

```css
.card {
  position: relative;
}

.badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
}
```

Damit kannst du beispielsweise Badges, Icons oder Overlays bauen.

---

# 9. Responsive Design ⭐⭐⭐⭐⭐

**Sehr wichtig.**

Eine Website muss nicht nur auf deinem 1440px-Monitor gut aussehen.

Du solltest verstehen:

```css
@media (max-width: 768px) {
  ...
}
```

Zum Beispiel:

```css
.hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
  }
}
```

Noch wichtiger: **Mobile-first** verstehen.

```css
.hero {
  grid-template-columns: 1fr;
}

@media (min-width: 768px) {
  .hero {
    grid-template-columns: 1fr 1fr;
  }
}
```

---

# 10. `:hover`, `:focus`, `:active` ⭐⭐⭐⭐

Für interaktive Elemente:

```css
button {
  background: blue;
}

button:hover {
  background: darkblue;
}
```

Aber auch:

```css
button:focus
button:active

a:hover
input:focus
```

Gerade `:focus` solltest du nicht vergessen, weil Tastaturbedienung wichtig ist.

---

# 11. Transitions ⭐⭐⭐⭐

Damit aus einer funktionierenden Website eine etwas „polished“ Website wird:

```css
button {
  transition: 0.2s ease;
}

button:hover {
  transform: translateY(-2px);
}
```

Du solltest kennen:

```css
transition
transform
```

und später:

```css
animation
@keyframes
```

---

# 12. Pseudo-Elemente

Sehr nützlich:

```css
::before
::after
```

Beispielsweise:

```css
.title::after {
  content: "";
  display: block;
  width: 50px;
  height: 4px;
  background: blue;
}
```

Damit kannst du viele kleine Design-Elemente erzeugen, ohne zusätzliches HTML.

---

# 13. CSS-Funktionen ⭐⭐⭐⭐

Ein paar davon sind extrem wertvoll:

```css
calc()
min()
max()
clamp()
```

Besonders:

```css
h1 {
  font-size: clamp(2.5rem, 5vw, 5rem);
}
```

Das ist für responsive Landingpages **richtig gut**.

---

# 14. `overflow`

Solltest du kennen:

```css
overflow: hidden;
overflow: auto;
overflow-x: auto;
```

Gerade bei Bildern, Karten und dekorativen Elementen häufig relevant.

---

# 🧠 Was ich NICHT am Anfang lernen würde

Du brauchst für einfache Websites erstmal nicht:

- komplizierte CSS-Animationssysteme
    
- CSS Houdini
    
- komplexe `clip-path`-Konstruktionen
    
- ausgefallene CSS-Tricks
    
- Sass/SCSS
    
- Tailwind
    
- Bootstrap
    
- CSS-in-JS
    
- komplizierte Accessibility-APIs
    
- irgendwelche riesigen Frameworks
    

Erst **HTML + CSS richtig gut**, dann JavaScript.

---

# 🏆 Meine persönliche „HTML/CSS für schöne Websites“-Checkliste

Wenn du diese Dinge wirklich beherrschst, kannst du schon erstaunlich viel:

### HTML

-  Semantisches HTML
    
-  `header`
    
-  `nav`
    
-  `main`
    
-  `section`
    
-  `article`
    
-  `aside`
    
-  `footer`
    
-  `div`
    
-  `span`
    
-  Überschriften
    
-  Text
    
-  Links
    
-  Bilder
    
-  Buttons
    
-  Listen
    
-  Formulare
    
-  `alt`
    
-  sinnvolle HTML-Hierarchie
    

### CSS

-  Selektoren
    
-  Klassen
    
-  `box-sizing`
    
-  Box Model
    
-  `margin`
    
-  `padding`
    
-  `border`
    
-  `width` / `height`
    
-  `max-width`
    
-  Farben
    
-  Typografie
    
-  `rem`
    
-  CSS Variables
    
-  **Flexbox**
    
-  **Grid**
    
-  `gap`
    
-  `position`
    
-  `z-index`
    
-  `border-radius`
    
-  `box-shadow`
    
-  `background`
    
-  `object-fit`
    
-  `overflow`
    
-  `:hover`
    
-  `:focus`
    
-  `::before` / `::after`
    
-  `transition`
    
-  `transform`
    
-  Media Queries
    
-  Responsive Design
    
-  `clamp()`
    
-  `min()` / `max()` / `calc()`