# Kapitel MV* Architekturmuster 

**Author: **  
Alexander Heinisch

## Architekturmuster

Wie strukturiert und organisiert man (große) Softwaresysteme in geeigneter Weise, so dass diese wartbar, testbar, erweiterbar und wiederverwendbar sind und so dass das System parallel von mehreren Menschen entwickelt werden kann?

## Entwurfsmuster vs. Architekturmuster

**Entwurfsmuster** sind Richtlinien, wie man gängige Probleme bei der Implementierung eines Softwaresystems löst.

**Architekturmuster** sind Richtlinien, um Struktur und Verhalten von Softwaresystemen abstrakt zu modellieren. Außerdem Richtlinien, wie die Interaktion zwischen Teilen des Softwaresystems(Pakete,Subsystemen,Server, Clients, Datenbanken) stattfinden soll.

## Interaktive Softwaresysteme mit GUI

In den meisten Fällen besteht eine Benutzerschnittstelle aus 2-3 Grundbausteinen

1. Eingabe/Ausgabe (View)
2. Verarbeitung (Model)
3. Datenbank (optional)

![](vorlesung12/bilder/Bild1.png)

Mögliche Abläufe könnten sein  
Eingabe -> Verarbeitung -> Ausgabe  
Eingabe -> Verarbeitung -> Datenbank -> Verarbeitung -> Ausgabe  
Um ein gutes Programm zu schreiben ist eine saubere Trennung dieser Bausteine notwendig!    

Beispiel für „ungute“ Softwarestruktur bzw. Aufteilung der Programmlogik: 

- GUI enthält Button.
- Event-Listener für Button wird in der GUI-Klasse implementiert (Callback). 
- Dort wird dann Geschäftslogik implementiert.

Geschäftslogik ist damit nicht benutzbar für andere Teile des Softwaresystems und nicht testbar.



## MV*-Architekturmuster

Lösungen für das genannte Problem führen zu Model-View-* Ansätzen 

Architekturmuster für interaktive Anwendungen mit GUI

MV*-Vorteile

- SingleResponsibilty Principle: Separiert Logik, Präsentation und Daten
- Separation of concerns (insbesondere gut für große Softwaresysteme mit vielen Software-Entwicklern)
- Wartbarkeit, Erweiterbarkeit, Austauschbarkeit, Testbarkeit
- Unterschiedliche Visualisierungen der Daten (Text, Grafik, etc.)

![Baum einiger MV*Architekturen](vorlesung12/bilder/bild2.png)

## Model-View-Controller



- Model enthält Geschäftslogik und Zustandsinformation der Softwareanwendung.

- View stellt die Daten des Models dar, ist also „abhängig“ vom Model. Die View ist Beobachter des Zustands, um den aktuellen Zustand darzustellen; es kann viele Views für ein Model geben. HTML, JSF, Swing, JavaFX 

  ![View Beispiel](vorlesung12/bilder/bild3.png)

- Controller. Zwischenschicht, die die Eingaben aus der View verarbeitet und zwischen View und einem oder mehreren Models vermittelt. Ein Controller legt das Verhalten der Software auf Benutzereingaben fest und kann für unterschiedliche Views benutzt werden. Wichtig: Im Controller steckt keine Geschäftslogik.

### Struktur

#### View

- (Graphische)Präsentation (Style, Layout) der Daten
- Interaktion mit dem Nutzer. Nutzeraktionen werden an Controller weitergegeben
- Statusänderung der View über Abfrage am Model 
- Implementierung von Logik in der View (=GUI-Logik)
  - Animation, Formatierung, Validierung, Aus/Einblenden von Feldern in Abhängigkeit des Zustands
- Fehler bei der Implementierung von Logik
  - Implementierung von Geschäftslogik in der View
  - Aufrufe von Speicherfunktionen des Models

#### Model

- Enthält Daten und Geschäftslogik
- Kennt nicht die konkreten Views (lose Kopplung)
- Jede Änderung der Daten verursacht Aktualisierung der Views

#### Controller

- Verbindet als Zwischenschicht die View und Model. Enthält Steuerungslogik. Enthält keine Geschäftslogik.
- Reagiert auf Nutzereingaben (Tastatureingaben, Mausklicks, etc.)
- Ruft Geschäftslogik vom Model (Delegation) auf und selektiert Views
- Ein Controller kann für verschiedene Views verwendet werden

### Zwei Arten von MVC

Die beiden unterscheiden sich nur in der Synchronisierung der Daten von Model und View.

- Passive Model
  - Nur der Controller manipuliert das Model und informiert die View, dass sich das Model geändert hat und dass sie sich „updaten“ soll. Die View holt dann Daten vom Model
- Active Model
  - Das Model hat Beobachter, nämlich die View(s). Wenn sich das Model ändert, informiert das Model die Beobachter, sich auf den neuesten Model-Stand zu bringen.
  - Sinnvoll, wenn Model nicht nur durch den Controller verändert wird
  - Form des Observer-Entwurfsmusters

#### Active MVC

##### Ablauf Active MVC

- In der View tritt ein Ereignis auf. Der Controller wird informiert.
- Controller steuert Änderungen des Models
- Model teilt allen Views mit, dass eine Änderung aufgetreten ist
- Views stellen den aktuellen Zustand dar

![](vorlesung12/bilder/bild4.png)

##### Implementierungsbeispiel

- Das Model und die View implementieren das Beobachter-Muster(Publish-Subscribe)
- Das Model ist das beobachtete Objekt und die Beobachter (Views) können sich beim Model registrieren
- Das Model hat 1...n Beobachter, nämlich die Views
- Datenänderung über Update-Methode der Views

![](vorlesung12/bilder/bild5.png)

#### Passive MVC

##### Ablauf passive MVC

- In der View tritt ein Ereignis aus. Der Controller wird informiert.
- Controller steuert Änderungen des Models
- Controller teilt den Views mit, dass eine Änderung aufgetreten ist
- Views stellen den aktuellen zustand dar

#### Vergleich von Active und Passive MVC

##### Active Model (=Observer Pattern)

![](vorlesung12/bilder/bild6.png)

##### Passive Model (=Flow)

![](vorlesung12/bilder/bild7.png)

### MVC in verteilten Systemen (hier Web)

- MVC wurde für Desktop-Anwendungen entwickelt, 
  - die Software läuft auf einem Computer in einem Prozess 
- Als das WWW aufkam, wurde MVC für Webanwendungen genutzt  
- HTTP ist zustandslos. Notwendigkeit von Sessions zwischen Client und Server  
- MVC in verteilten Systemen wird „VCM-Architektur“ genannt.
- der Controller enthält Steuerungslogik

![](vorlesung12/bilder/bild8.png)

![](vorlesung12/bilder/bild9.png)

![](vorlesung12/bilder/bild10.png)

### RIA-MVC

Die Geschäfts- und Steuerungslogik wird auf dem Client ausgeführt. 
Das Client-Model synchronisiert sich mit dem Model, das auf dem Server gespeichert wird.

![](vorlesung12/bilder/bild11.png)

## MVP

MVC hat Nachteile: 

- Die View kennt den Controller und das Model. Bei Änderungen sind viele Klassen zu ändern
- Komplexe Views haben unterschiedliche Models, was zu vielen Abhängigkeiten und langsamer Darstellung führt
- UI-Logik über View und Controller und manchmal über Model verteilt
- UI-Logik in der View ist schlecht zu testen. UI-Logik gehört aber nicht in das Model. Beispiel: user.forename und  user.lastname sollen in der GUI als user.fullname angezeigt werden. Gehört diese Logik in die GUI oder in das Model?

MVP beseitigt diese Probleme

- Die View kennt nur den Presenter und informiert den Presenter über Ereignisse (Button-Klicks etc.)
- Der Presenter implementiert UI-Logik
- Presenter kennt nur eine Abstraktion (=Interface) der View
- Nur der Presenter kennt das Model. Die View kennt das Model nicht.
- Um View und Presenter testfähig zu machen, werden Interfaces verwendet
- View und Presenter kennen sich gegenseitig.1-zu-1-Beziehung.

![](vorlesung12/bilder/bild12.png)

### Struktur

#### Model

- Schnittstelle zu den Daten(„Repository“). „Kommunikation“ mit Datenbank
- Enthält Validierungslogik und Geschäftslogik

#### View

- Visualisierung der Daten und Validierungslogik für Eingabe der View.
- Mehrere Views möglich. Jede View hat einen Presenter
- Kann von einem „GUI-Designer“ separat entwickelt werden
- GUI-Event-Listener, der „Klick“-Ereignisse etc. an den Presenter weiterleitet (Im MVC ist dies Aufgabe des Controllers)
- Interface der View sollte keine „get“-Methoden enthalten, sondern die Werte als Parameter bei Methodenaufrufen an den Presentergeben
- Interface enthält „set“-und „add“-Methoden zum Setzen von anzuzeigenden Werten

#### Presenter

- Hält Referenz auf Model und View. Presenter agiert als „Mediator“. 
- Macht sich bei der View bekannt („setPresenter()“)
- Enthält Steuerungslogik und „holt“ Daten aus dem Model
- Formatiert Daten für die GUI und ändert die View
- In der Regel gibt es einen Presenter für eine View. Komplexe Views können mehrere Presenter besitzen.

![](vorlesung12/bilder/bild13.png)

![](vorlesung12/bilder/bild14.png)

![](vorlesung12/bilder/bild15.png)

### MVP-Varianten

1. MVP Passive View: „dumme“ View, die nur zur Anzeige dient. Presenter ruft Methoden der View auf, umgeänderte Model-Daten anzuzeigen. Interaktion mit Model ausschließlich durch den Presenter. Die View ist ausschließlich durch Presenter geändert.  
  ![MVP Passive View](vorlesung12/bilder/bild16.png)
2. MVP Supervising Presenter: Intelligentere View, die auf das Model zugreifen kann. Presenter kann bei komplexeren Updates aber immer noch auf die View zugreifen. Die View wird durch den Presenter und durch simples Databinding zwischen View und Model geändert.  
  ![MVP Supervising Presenter](vorlesung12/bilder/bild17.png)

### Vorteile

- Bessere Möglichkeiten für automatisierte Tests (auch durch Benutzung von Interfaces)
- Lose Kopplung. View und Model kennen sich nicht und sind unabhängig voneinander.
- Separation of Concerns. “Aspekte” können unabhängig voneinander und parallel entwickelt und getestet werden.
- Wiederverwendung. Insbesondere der Geschäftslogik im Model.
- Flexibilität. Views können einfach ausgetauscht oder verändert werden.

### Nachteile

- Große Anzahl von Interfaces
- Presenter können groß werden, weil auch die UI-Logik im Presenter festgelegt ist

## MVVM

MVVM erlaubt dem GUI-Designer eigene Programmierung durch ereignisgesteuerte und deklarative Programmierung.

das ViewModel stellt Datenströme zur Verfügung, an denen sich die View binden kann.

Das ViewModel kennt ein oder mehrere Models, aber keine View, denn die View „bindet“ sich zur Laufzeit an das ViewModel.

Das ViewModel ist nicht View abhängig und besitzt daher keine Referenz zu einer View. (somit werden zur Implementierung auch keine Interfaces mehr benötigt)

Die View kennt nur das ViewModel und keine Models.

Das ViewModel speichert auch den UI-Zustand

Die View benutzt das ViewModel, um über Eingaben des Benutzers zu informieren und entsprechende Aktionen auszulösen

Daten werden im ViewModel geändert und dann durch Databinding in der View dargestellt

![](vorlesung12/bilder/bild18.png)

![](vorlesung12/bilder/bild19.png)

![](vorlesung12/bilder/bild20.png)

### Struktur

#### ViewModel

- Nicht visuelle Klasse, die die Präsentations-Logik enthält
- Hält keine direkte Referenz auf die View 
- Koordiniert die Interaktion der View mit dem Model
- Kann Datenvalidierungen und Fehler Reporting vornehmen
- Änderungen im Model werden durch das ViewModel in der View synchronisiert und umgekehrt
- Das ViewModel speichert auch den Zustand der View und enthält UI-Logik, wodurch die Logik in der View minimiert wird
- Das ViewModel holt Daten aus dem Model und führt darauf UI-Logik durch

#### Model

- Nicht-visuelle Klasse, die die Daten und die Geschäftslogik der Anwendung kapselt 
- Kennt weder das ViewModel noch die View 
- Sollte keine Use-Case-spezifische Logik enthalten
- Teilt anderen Teilen des Softwaresystems mit, wenn sich der Modelzustand ändert
- Kann und sollte Datenvalidierungslogik enthalten

#### View

- Visuelle Klasse, die Aussehen und Layout der Daten bestimmt
- Präsentiert UI-Verhalten(Animation und Transitionen)
- Jede View besitzt eine Referenz zu einem oder mehreren ViewModels

### Databinding im Detail

Was ist Databinding?
Als databinding wird die automatische Weitergabe von Daten zwischen Objekten bezeichnet.  
Wenn sich also bei dem Quellobjekt der Wert ändert wird automatisch diese Änderung auch an die Objekte verteilt, welche mit dieser Quelle verbunden sind. Dies wird verwendet um Werte automatisch in die UI zu bringen, wenn es Änderungen gab. 

![Databinding](vorlesung12/bilder/bild21.png)

#### Databinding Varianten: 

| Binding          | Beschreibung                             |
| ---------------- | ---------------------------------------- |
| One Time binding | zeigt die Daten einmal an, wenn das Binding erzeugt wird |
| One Way binding  | zeigt die Daten an, wenn das Binding erzeugt wird und immer dann, wenn die Daten sich ändern |
| Two Way binding  | Änderungen werden in beide Richtungen propagiert |

### MVVM Vorteile / Nachteile

#### Vorteile

- Separation of concerns
- UnitTests einfach zu schreiben
- GUI-Designer und Entwickler können parallel entwickeln
- Die GUI kann ohne große Problem neu entworfen werden 

#### Nachteile

- Schwer zu debuggen, weil viele Abläufe automatisch ablaufen
- Die Performanz der Anwendungen kann durch das Databinding negativ beeinflusst werden

## Zusammenfassung Model-View-*

**Model**: Business Objekte und Geschäftslogik

**View**: Grafische Schnittstelle zum Benutzer

**Presenter**

- 1-zu-1 Beziehung zwischen View und Presenter
- Jede View implementiert ein Interface, durch das der Presenter mit der View interagieren kann. Jede View hat eine Referenz zum Presenter und kann dort Steuerungslogik initiieren.

**ViewModel** 

- n-zu-1 Beziehung zwischen View und ViewModel
- View interagiert mit dem ViewModel durch Bindung an Attribute und Funktionen

**Controller**

- n-zu-1-Beziehung zwischen View und Controller
- In der Passive Model-Variante wird die Kommunikation von View und Model komplett durch den Controller geschleust.
- In der Active-Model-Variante werden die Updates durch das Observer-Pattern abgehandelt.

![Die unterschiedlichen MV* grafisch verglichen](vorlesung12/bilder/bild22.png)

### Wann sich welche MV* anbietet

| MVP                                      | MVC                                      | MVVM                                     |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| View interagiert mit dem Presenter durch Aufruf von Presenter-Funktionen | View sendet Eingabe Ereignisse an den Controller über "CallbackHandler" | View bindet sich direkt an das ViewModel |
| Der Presenter interagiert mit der View durch Aufruf von Interface-Funktionen, die durch die View implementiert sind | Die View erhält in der "active Model"-Variante Zustandsänderungen direkt vom Model ohne Aktivität des Controllers | Änderungen in der View werden direkt in das ViewModel geschrieben und umgekehrt |
| Zu benutzen, wenn ein Databinding nicht möglich ist | Active Model zu benutzen, wenn das Model von unterschiedlichen Prozessen verändert wird | Zu benutzen, wenn Databinding möglich    |

