name: Kotlin
class: center, middle
background-image: url(image.jpg)

.center[![Right-aligned image](Kotlin-logo.png)] 
# Kotlin



Alexander Bergmann

---
## Inhaltsverzeichnis

1. Geschichte
2. Vorteile
3. Hello World - Kotlinstyle
4. Code-Beispiele
5. Quellen

???

---

## Geschichte 

```xml
"Kotlin ist auch eine Insel"
```

- Kotlin ist eine statisch typisierte Programmiersprache, die
  -  in Bytecode für die Java Virtual Machine (JVM) übersetzt werden kann
  -  aber auch in JavaScript-Quellcode transformiert werden kann
- Hauptsächlich wurde die Sprache von den in Sankt Petersburg ansässigen JetBrains-Programmierern entwickelt. (intelliJ-IDEA, PHPStorm etc.)
- 2011 von JetBrains der Öffentlichkeit präsentiert
- Daher stammt auch der Name: *Kotlin ist eine Insel vor St. Petersburg.* 
- Die Sprache ist syntaktisch nicht zu Java kompatibel
- Findet Anwendung in Androidentwicklung und immer mehr auch auf Servern

???
- Bei der statischen Typisierung wird im Gegensatz zur dynamischen Typisierung der Datentyp von Variablen und anderen Programmbausteinen schon während der Kompilierung festgelegt.
- https://de.wikipedia.org/wiki/Kotlin_(Insel) 
---

## Vorteile

- Kompakteren Code schreiben
- Null-Sicherheit
- einheitliches Typsystem
- Properties statt Getter und Setter
- Strings mit eingebetten Variablen

???

---

## Hello World

```kotlin
fun main(args: Array<String>) {		// Einsprungpunkt (Main-Funktion) 
  
  val name = args.getOrElse(0){"Welt"} 
  
  println("Hallo $name!")        	// Gebe den String 'Hallo Welt!' aus

}
```

???

- Semikolon
- intelliJ gibt bei Semikolon sogar eine Warnung aus (nicht "kotlinesk")

---

class:middle

### Fast alles ist ein Ausdruck

```kotlin
val color = 
	if (stock == 0) color.RED
	else if (stock < 10) Color.YELLOW
	else Color.GREEN
```

### switch gefällig ?

```kotlin
val color = when(x) {
  0 -> "nix"
  1, 2 -> "eins oder zwei"
  in 1..9 -> "einstellig"
  else -> "irgendwas"
}
```

->*Kein Fall-through*

???

- Unterschied val und var hier erklären

---

class:middle

### Code Lesbarkeit erhöhen

Java:

```java
for(Item item : collection)
```

Kotlin:

```kotlin
for(item in collection)
```

???

---

class:middle

### Nie wieder NullPointerExceptions

Der Compiler stellt sicher das eine Reference nie den Wert ***null*** annehmen kann, ausser es explizit erlaubt.

```kotlin
val name: String? = null
val city: String = null // Fehler!
```

???

---

class:middle

### Just wanna have fun

Funktionen

```kotlin
fun max (a: Int = 0, b: Int = 1): Int = if (a > b) a else b

// Aufruf
var maximum = max(b = 3, a = 5) 
```

Erweiterungs Funktionen

```kotlin
fun Int.times(action: (Int) -> Unit){
  for (i in 1..this) {
    action(i)
  }
}
// Aufruf
5.times {print(it)}
```

???

- Kein void , dafür aber Unit existent
- Variablendeklaration erklären
- Funktionen höherer Ordnung möglich : Funktion als Parameter
- Erweiterung ohne von Int abzuleiten

---

### Klassen

```kotlin
data class Point(x: Int, y: Int) {
  init {
    require(x >=0)
    require(y >=0)
  }
}
```

Durch Schlüsselwort **data** leifert der Compiler equals(), hashCode(),toString ...etc, so wie Properties gleich mit.

```kotlin
//getter setter implementieren
class Message {
  var = text: String = "hello"
	get() = text.toUpperCase()
	set(value) {
  		text = value.toUpperCase();
	}
}

// benutzen
val m = Massage()
m.text = "hi"
println(m.text)

```

???

- vergleichbarer Code in Java wäre um die 50 Zeilen lang
---

### Vererbung

```kotlin
open class A (val y: Int) {
	// überschreibbar
	open fun foo {
      println("A")
	}
	// nicht überschreibbar
	fun bar (x : Int) = y * x
}

// B erbt von a 
class B(val w: Int, y: Int) : A(y)

```

???

- ohne open grundsätlich nicht vererbbar oder überschreibbar

---

### Probier es aus 

- http://try.kotlinlang.org/



---

## Quellen

- https://de.wikipedia.org/wiki/Kotlin_(Programmiersprache)

- c'T Magazin 15/17, 16/17

---
class: center, middle

## Vielen Dank 
Fragen ?
