## Sequenzdiagramme

**Autoren:**

 Nikita Loetkemann, André Matutat, Daniel Räder

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

![Sequenzdiagramm Beispiel](vorlesung8/Bilder/sequenzdiagramm_beispiel1.png)

Hier dargestellt sind zwei einfache Beispiele für Sequenzdiagramme.
Diese Diagramme werden von links nach rechts , oben nach unten gelesen, wobei die vertikale Achse den zeitlichen Ablauf repräsentiert.

#### Objekte
Objekte werden dort zuerst eingezeichnet wo sie erstellt werden, in unseren Beispielen existieren alle Objekte von Beginn an.
- Die gestrichelte **Lebenslinie** unter einem Objekt zeigt seinen Lebenslauf, an ihrem Ende steht ein X, als Kennzeichen für die Zerstörung des Objekts
- Vertikale Balken entlang dieser Lebenslinie, sogenannte **Aktivierungsbalken** repräsentieren die Abarbeitung einer Methode des Objekt
- Diese Balken können leicht versetzt sein, wenn es sich um Aufrufe von Unter-Methoden im gleichen Objekt handelt
- Der Aufruf dieser Methoden geschieht über horizontale Pfeile, **Botschaften**, welche zwischen Objekten eingezeichnet werden, diese werden mit dem Namen der Methode beschriftet
- Die Rückgabe der Funktion kennzeichnet ein *gestrichelter* Pfeil in entgegengesetzter Richtung.
- Diese Botschaften können des weiteren mit **\*** und/oder **[condition]** markiert sein, um einen wiederholenden oder konditionalen Aufruf zu kennzeichnen