# Entwurfsmuster



### Builder-Pattern

#### Beschreibung

- zu einem komplexen Objekt existieren unterschiedliche Darstellungen 
- die Konstruktion eines komplexen Objekts ist unabhängig von der Erzeugung der Bestandteile
- Trennung des Erzeugungsprozesses einer komplexen Objektstruktur von der internen Darstellung der Objektstruktur
- Es trennt die  Konstruktion komplexer  Objekte  vonderen Repräsentationen, wodurch die selben Konstruktionsprozesse wiederverwendet werden können
- Die Implementierungen der Konstruktion und der Repräsentationen werden isoliert  
- Builder versteckt interne Repräsentation vor dem Direktor  
- Neue Repräsentationen lassen sich leicht durch neue konkrete Builderklasse einfügen  
- Der Konstruktionsprozess wird an einer eindeutigen Stelle (im Direktor) gesteuert. Spätere Änderungen lassen sich ohne Änderung der Klienten realisieren  

#### Akteure

- Builder 
  - spezifiziert abstrakte Schnittstelle zur Erzeugung der Teile eines komplexen Objekts 
- ConcreteBuilder 
  - implementiert die Schnittstelleund erzeugt die Einzelteile
  - Definiert und verwaltet die von ihm erzeugte Präsentation
- Director 
  - konstruiert das komplexe Objekt unter Verwendung der Schnittstelle des Builders
  - Kennt die benötigte Baureihenfolge  
- Product
  - Ist das komplexe Objekt  

![](bilder/Bild40.png)

![](bilder/Bild41.png)

#### Beispiel für Anwendung

Lesen von RTF-Dateien und Konvertieren nach LaTex, Text, PDF, etc.

![](bilder/Bild42.png)

### Template Method

#### Beschreibung

- Abstrakte Klasse legt Ablauf des Algorithmus vor („Template Method“), eine Serie von Aufrufen abstrakter Methoden
- Subklassen müssen diese abstrakten Methoden implementieren, je nach konkretem Klasse
- Template Methode muss final sein, damit sie nicht überschrieben werden kann
- Damit ist der Ablauf des Algorithmus bei allen gleich, aber die Verantwortung liegt bei den Subklassen

![](bilder/Bild43.png)

#### Beispiel für Anwendung

![](bilder/Bild44.png)

```java
public abstract class AbstractReader {
  public final Result decode(Image image){
    Row row = scan(image);
    if(!row.isSuccess()){
      reverseImage(image);
      row = scan(image);
    }
    Result result = decodeRow(row);
    return result;
  }
  public abstract Row scan(Image image);
  public abstract void reverseImage(Image image);
  public abstract Result decodeRow(Row row);
}
```

### Visitor

- Zweck
  - Stellt eine allgemeine Möglichkeit zur Traversierung einer beliebigen Objektstruktur zur Verfügung
  - Kapselt eine auf den Elementen einer Objektstruktur auszuführende Operation als ein Objekt.
  - Trennt die Datenstruktur von den Operationen, die auf der Objektstruktur auszuführen sind
  - Ermöglicht es, eine neue Operation zu definieren, ohne die Klassen der von ihr bearbeiteten Elemente zu verändern.
- Beispiel:
  - Compilerbau: Erzeugen desQuellcodes aus abstraktem Syntaxbaum
  - Interpreter: Berechne dynamisch dasErgebnis eines Ausdrucks

![](bilder/Bild46.png)

#### Implementierung

- Visitor
  - deklariert für jede Klasse konkreter Elemente eine Besuchsfunktion
- ConcreteVisitor
  - implementiert Besuchsfunktionen
  - jede Besuchsfunktion ist ein Fragment des Algorithmus, welcher auf der gesamten Objektstruktur angewendet wird
  - lokaler Zustand des Besuchers dient als Kontext für den Algorithmus
- Element
  - deklariert eine Schnittstelle zum Empfang eines Besuchers
- ConcreteElement
  - implementiert den Empfang eines Besuchers
  - Definiert, wie das konkrete Element traversiert wird
  - Gibt Visitor an Kindelement weiter

![](bilder/Bild47.png)

### Architekturmuster vs.Entwurfsmuster (Active Model View Controller)

(Active MVC setzt sich aus drei Entwurfsmustern zusammen)

![](bilder/Bild48.png)



- View 
  - implementiert bei Bedarf das Composite Pattern
- Model
  - Implementiert Beobachter-Muster(Publish-Subscribe)
  - Model ist das beobachtete Objekt
  - Hat 1...n Beobachter, nämlich die Views
  - Das Model bietet einen Mechanismus, bei denen sich die Beobachter registrieren können
  - Datenänderung über update-Methode der Views
- Controller
  - Kann bei Bedarf Strategy Pattern verwenden

## Zusammenfassung

### Abstrakte Fabrik (Abstract Factory)

Biete eine Schnittstelle zum Erzeugen von Familien verwanter oder voneinander abhängiger Objekte, ohne ihre konkrete Klassen zu benennen.

### Adapter 

Passe die Schnittstelle einer Klasse an eine andere von ihren Klienten erwartete Schnittstelle an. Das Adaptermuster läßt Klassen zusammenarbeiten, die wegen inkompatibler Schnittstellen ansonsten dazu nicht inder Lage wären.

### Befehl (Command)

Kapsle einen Befehl als ein Objekt. Dies ermöglicht es, Klienten mit verschiedenen Anfragen zu parametrieren, Operationen in eine Queue zu stellen, ein Logbuch zu führen und Operationen rückgägnig zu machen.

### Beobachter (Observer)

Definiere eine 1-zu-n-Abhängigkeit zwischen Objekten, so daß die Änderungen des Zustands eines Objektes dazu führt, daß alle abhängigen Objekte benachrichtigt und automatisch aktualisiert werden.

### Besucher (Visitor)

Kapsle eine auf den Elementen einer Obhektstruktur auszuführende Operation zu definieren als ein Objekt. Das Besuchermuster ermöglicht es Ihnen, eine neue Operation zu definieren, ohne die klassen der von ihr bearbeiteten Elemente zu verändern.

### Brücke (Bridge)

Entkopple eine Abstraktion von ihrer Implementierung, so daß beide unabhängig voneinander variiert werden können.

### Dekorierer (Decorator)

Erweitere ein Objekt dynamisch um Zuständigkeiten. Dekorierer bieten eine flexible Alternative zur Unterklassenbildung, um die Funktionalität einer Klasse zu erweitern.

### Erbauer (Builder)

Trenne die Konstruktion eines komplexen Objekts von seiner Repräsentation, so daß derselbe Konstruktionsprozeß unterschiedliche repräsentationen erzeugen kann.

### Fabrikmethode (Factory Method)

Definiere eine Klassenschnittstelle mit Operationen zum Erzeugen eines Objekts, aber lasse Unterklassen entscheiden, von welcher Klasse das zu erzeugende Objekt ist. Fabrikmethoden ermöglichen es einer Klasse, die Erzeugung von Objekten an Unterklassen zu delegieren.

### Fassade (Facade)

Biete eine einheitliche Schnittstelle zu einer Menge von Schnittstellen eines Subsystems. Die Fassadenklasse definiert eine abstrakte Schnittstelle, welche die Verwendung des Subsystem vereinfacht.

### Fliegengewicht (Flyweight)

Nutze Objekte kleinster Granularität gemeinsam, um große Mengen von ihren effizient verwenden zu können.

### Interpreter

Definiere für eine gegebene Sprache eine Repräsentation der Grammatik sowie einen Interpreter, der die Repräsentation nutzt, um Sätze in der Sprache zu interpretieren.

### Iterator 

Ermögliche den sequentiellen zugriff auf die Elemente eines zusammengesetzten Objekts, ohne seine zugrundeliegende Repräsentation offenzulegen.

### Kompositum (Composite)

Füge Objekte zu Baumstrukturen zusammen, um Teil-Ganzes-Hierarchien zu repräsentieren. Das Kompositionsmuster ermöglicht es Klienten, einzelne Objekte sowie Kompositionen von Objekten einheitlich zu behandeln.

### Memento (Memento)

Erfasse und externalisieren den internen Zustand eines Objekts, ohne seine Kapselung zu verletzen, so daß das Objekt später in diesen Zustand zurückversetzt werden kann.

### Prototyp 

Bestimme die Arten zu erzeugender Objekte durch die Verwendung eines prototypischen Exemplars, und erzeuge neue Objekte durch Kopieren dieses Prototypen.

### Proxy 

Kontrollieren den Zugriff auf ein Objekt mit Hilfe eines vorgelagerten Stellvertreterobjekts.

### Schablonenmethode (Template Method)

Definieren das Skelett eines Algorithmus in einer Operation und delegiere einzelne Schritte an Unterklassen. Die Verwendung einer Schablonenmethode ermöglicht es Unterklassen, bestimmte Schritte eines Algorithmus zu überschreiben, ohne seine Striktur zu verändern.

### Singleton

Sichere ab, daß eine Klasse genau ein Exemplar besitzt, und stelle einen globalen Zugriffspunkt darauf bereit.

### Strategie (Strategy)

Definiere eine familie von Algorithmen, kapsele jeden einzelnen und mache sie austauschbar. Das Strategiemuster ermöglicht es, den Algorithmus unabhängig von ihn nutzenden Klienten zu variieren.

### Vermittler (Mediator)

Definiere ein Objekt, welches das Zusammenspiel einer Menge von Objekten in sich kapselt. Vermittler fördern lose Kopplung, indem sie Objekte davon abhalten, auf einander explizit Bezug zu nehmen. Sie ermöglichen es Ihnen, das Zusammenspiel der Objekte von ihnen unabhängig zu variieren.

### Zustand (State)

Ermögliche es einem Objekt, sein Verhalten zu ändern, wenn sein interner Zustand sich ändert. Es wird so aussehen, als ob das Objekt seine Klasse gewechselt hat.

### Zuständigkeitskette (Chain of Responsibility)

Vermeide die Kopplung des Auslösers einer Anfrage an seinen Empfänger, indem mehr als ein Objekt die Möglichkeit erhällt, die Anfragen zu erledigen. Verkette die empfangenden Objekte, und leite die Anfrage an der Kette entlang, bis ein Objekt sie erledigt.

### Vergleich von Strategy und Template Pattern 

![](bilder/Bild45.png)