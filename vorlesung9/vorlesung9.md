## Sequenzdiagramme

**Autoren:**

 Nikita Lötkemann, André Matutat, Daniel Räder

### Was sind Sequenzdiagramme?

Sequenzdiagramme dienen der Darstellung von Kommunikation und Interaktion von einzelnen Elementen in einem System. Sie verbinden somit die zuvor erklärten Aktivitäts- und Klassendiagramme, da sie verifizieren, ob die im Aktivitätsdiagramm beschriebenen Abläufe in den Methoden des Klassendiagramms zureichend abgebildet sind.

Die Diagramme dokumentieren hierfür die Interaktion von einzelnen Objekten mit ihren Methoden, ihre Erstellung und/oder Zerstörung  und den zeitlichen Ablauf in dem diese Ereignisse ablaufen, eine **Sequenz**, entsprechend der Name.

### Szenarien

Entscheidend ist, dass ein jedes Sequenzdiagramm immer nur für ein bestimmtes **Szenario** gilt, das heißt, eine spezifische, beispielhafte, Abfolge von Funktionen und Interaktionen in einem System.
Zu jedem Szenario gehört ein eigenes Diagramm, und dienen der Festlegung von Testfällen auf Basis welcher, im späteren Verlauf der Entwicklung, Integrationstests erstellt werden können.

Szenarien basieren zumeist auf zuvor beschriebenen Use-Case-Definitionen und lassen sich somit in *Normalfälle* und *Ausnahmefälle* unterteilen
- Normalfälle (und ggf. Alternativfälle) dienen zur Diskussion mit Anwendern und anderen Mitgliedern des Projekts
- Ausnahmefälle finden mehr Verwendung bei den Entwicklern um mögliche Fehlerquellen zu identifizieren und abzufangen

Um aus einem Szenario ein Sequenzdiagramm abzuleiten folgt man einem einfachen Dreischrittprinzip:
1. Beteiligte Klassen Ermitteln
2. Aufgaben des Szenarios in Methoden abbilden/zerlegen
3. Reihenfolge der Operationen überprüfen und gewährleisten

Der dritte Schritt ist speziell bei der Interaktion verschiedener Module wichtig

### Aufbau und Notationselemente

![Sequenzdiagramm Beispiel 1](vorlesung9/Bilder/sequenzdiagramm_beispiel1.png)

![Sequenzdiagramm Beispiel 2](vorlesung9/Bilder/sequenzdiagramm_beispiel2.png)

Hier dargestellt sind zwei einfache Beispiele für Sequenzdiagramme.
Diese Diagramme werden von links nach rechts , oben nach unten gelesen, wobei die vertikale Achse den zeitlichen Ablauf repräsentiert.

#### Objekte
Objekte werden dort zuerst eingezeichnet wo sie erstellt werden, in unseren Beispielen existieren alle Objekte von Beginn an.
- Die gestrichelte **Lebenslinie** unter einem Objekt zeigt seinen Lebenslauf, an ihrem Ende steht ein X, als Kennzeichen für die Zerstörung des Objekts
- Vertikale Balken entlang dieser Lebenslinie, sogenannte **Aktivierungsbalken** repräsentieren die Abarbeitung einer Methode des Objekt
- Diese Balken können leicht versetzt sein, wenn es sich um Aufrufe von Unter-Methoden im gleichen Objekt handelt
- Ein Aktivierungsbalken zeigt an, ob ein Objekt aktiv ist, die Länge des Balkens zeigt die aktive Zeit des Prozesses
- Der Aufruf dieser Methoden geschieht über horizontale Pfeile, **Botschaften**, welche zwischen Objekten eingezeichnet werden, diese werden mit dem Namen der Methode beschriftet
- Die Rückgabe der Funktion kennzeichnet ein *gestrichelter* Pfeil in entgegengesetzter Richtung.
- Diese Botschaften können des weiteren mit **\*** und/oder **[condition]** markiert sein, um einen wiederholenden oder konditionalen Aufruf zu kennzeichnen
- Die Zeitlinie gilt für alle Objekte gleichzeitig, d.h. alle schreiten zur gleichen Zeit voran

####Nachrichten
 #####Synchrone Nachricht
 - Die Interaktion gilt zur gleichen Zeit für den Sender und den Empfänger
 - es geschieht alles ohne Verzögerung
 - wird dargestellt durch einen Pfeil mit ausgefüllter Spitze
#####Antwortnachricht für synchrone Nachrichten
- wird dargestellt durch einen gestrichelten Pfeil ohne ausgefüllter Spitze

#####Asynchrone Nachricht
 - es wird hier unterschieden zwischen Senden und Empfangen der Nachricht
 - Nachricht wird nicht direkt zugestellt, es kann Verzögerung geben
 - Empfänger muss nicht zwangsläufig bereit sein
 - wird dargestellt durch einen Pfeil ohne ausgefüllter Spitze

##### Methodenaufrufe



![methodenaufruf](./Bilder\methodenaufruf.PNG)

- Jeder Methodenaufruf ist eine Nachricht, mit Bedingungen und Anweisungen
- Methodenaufrufe sind die Kommunikation zwischen den Objekten und verbindet die Objekte mit einem Pfeil und einer Markierung
- Die Markierung besteht aus einer Bedingung, einer Variable, Name der Botschaft, den Argumenten und dem Typ: 
- (['Bedingung']')[Variable:=]NameBotschaft'('[Argumente]')' :Typ
- Die Variable nimmt das Ergebnis auf
- Der Pfeil zurück signalisiert, dass der Kontrollfluss an Aufrufer zurück geht
- Asynchrone Nachrichten haben keine Returns
- steht ein * vor einem Methodenaufruf(Nachricht), geht die Nachricht an alle Objekte, der entsprechenden Klasse

###Steuerungsoperatoren (kombinierte Fragmente)

#### Übersichtüber alle Steuerungsoperatoren 

|                             | Operator                             | Zweck                                    |
| --------------------------- | ------------------------------------ | ---------------------------------------- |
| Verzweigung und Schleifen   | alt<br>opt <br> loop <br>break       | Alternative Interaktion <br>Optionale Interaktion <br>Iterative Interaktion <br>Ausnahme-Interkation |
| Nebenläufigkeit und Ordnung | seq <br>strict<br>par<br>critical    | Schwache Ordnung <br>Strenge Ordnung <br>Nebenläufigkeit Interaktion <br>Atomare Interaktion |
| Filterung und Zusicherungen | ignore <br>consider<br>assert<br>neg | Irrelevante Interaktionsteile<br>Relevante Interatkionsteile <br>Zugesicherte Interaktion<br>Ungültige Interaktion |

#### Steuerungsoperatoren

#####Parallele Ausführung 

- Nebenläufig Abläufe

![par](vorlesung9/Bilder/par.PNG)

#####Iterative Ausführung

- die Operationen werden wiederholt

![loop](vorlesung9/Bilder/loop.PNG)



#####Bedingte Ausführung
- das Rechteck wird durch gestrichelte Linien in eine oder mehrere Bereiche aufgeteilt und enthält eine Bedingung in eckigen Klammern. Wenn mehrere Bedingungen wahr sind, werden alle ausgeführt. Falls alle Bedingungen falsch sind, werden die Ausführungen des Operators übergangen.

![lalt](vorlesung9/Bilder/alt.PNG)

#####Optionale Ausführung
- stellt eine Vereinfachung der bedingten Ausführung mit nur einem Unterbereich dar.

![lopt](vorlesung9/Bilder/opt.PNG)


#### Beispiel: Reklamation

![BeispielDiagramm](vorlesung9/Bilder/BeispielDiagramm.png)

###Best practices

- Indem **Sequenzdiagramm** steht die **zeitliche Abfolge** und die **Dynamik** im Vordergrund

- Zurbesseren Lesbarkeit werden Objekte mit den Lebenslinien und Nachrichten so angeordnet, dass das Diagramm von oben nach unten (wegen der Zeit) und vonl inks nach rechts (wegen der Schachtelung der Aufrufe) gelesen werden kann

- Steuerungsoperatoren **nur dann** verwenden, wenn der Ablaufkompliziert ist und Wiederholungen bzw. optionale oder parallele Ausführungen enthält


### Kommunikationsdiagramme

- Alternative zum Sequenzdiagramm
- beschreiben und visualisieren das grundsätzliche Zusammenspiel und die Beziehungen zwischen den Kommunikationspartnern (=Objekten)

#### Kommunitkationsdiagramm Beispiel

![KommunikationsdiagrammBeispiel](vorlesung9/Bilder/KommunikationsdiagrammBeispiel.png)

- Hinweis: Nummerierung: 1.1.a und 1.1.b markieren parallele Abläufe

### Zusammenfassung
  ![ZusammenfassungBild1](vorlesung9/Bilder/ZusammenfassungBild1.png)

  ![ZusammenfassungBild1](vorlesung9/Bilder/ZusammenfassungBild2.png)



