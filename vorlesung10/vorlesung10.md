# Weitere UML-Diagramme
 
 #### Autoren
 Jan Tschech, Marc Schwettmann, Florian Buller
 
 ### Objektdiagramme
 
 Ein Objektdiagramm wird die Instanziierung der Klassen eines Klassendiagramms und die zugehörige Belegung der Attribute dargestellt.

- Objektdiagramm
  - zeigt eine Momentaufnahme des Systemzustands zur Laufzeit an
  - zeigt die Ausprägungen von Klassen, Assoziationen und Attributen an
 
 ![objDia](vorlesung10/Bilder/objDia.png)
 
 ![objDia2](vorlesung10/Bilder/objDia2.png)
 
 - Assoziationen zwischen Klassen modellieren potenzielle Links
 - Kardinalitäten beschränken die Zahl der Links
 
 ![objDia3](vorlesung10/Bilder/objDia3.png)
 
 - Objekte werden durch Links miteinander verbunden
 
 ![objDia4](vorlesung10/Bilder/objDia4.png)
 
 ### Komponenten
 
 #### Software-Komponente
 
 Zur Wiederverwendung und Wartbarkeit gliedern Komponente das Softwaresystem in funktionale Bausteine. Zwecks Portabilität 
 werden Komponente implementierungsunabhängig definiert. Komponenten sollen leicht austauschbar sein und können von
 Zulieferern entwickelt werden, die Spezialisten in dem Aufgabenbereich sind. Desweiteren dienen Komponente zur
 parallelisierung bei der Entwicklung (die einzelnen Komponenten können parallel verfeinert und entwickelt werden) und dienen
 ebenfalls als Abgenzung zu einem Modul (Ein Modul ist eine Zusammenfassung von Operationen und Daten zur Realisierung einer
 abgeschlossenen Aufgabe). 
 
 ![komponente](vorlesung10/Bilder/komponente.png)
 
 ![komponente2](vorlesung10/Bilder/komponente2.png)
 
 #### Schnittstellen sind das Bindeglied zwischen den Komponenten
 
 Eine Schnittstelle besteht aus einer Menge von verschiedenen Operationen. Das Verhalten der Komponenten ist über eine
 Schnittstelle zugreifbar. Schnittstellen zwischen den Komponenten müssen klar definiert sein, man unterscheidet zwischen
 provided interface (wird durch Komponente angeboten) und required interface (wird von Komponente benötigt).
 Um eine geringe Kopplung zu gewähleisten, müssen die Schnittpunkte zwischen den Komponenten so gering wie möglich gehalten
 werden.
 Um eine hohe Kohäsion zu gewähleisten, müssen Verantwortlichkeiten sinnvoll auf die Komponenten aufgeteilt werden.
 Komponenten können bei Verwendung derselben Schnittstellen ohne Systemänderungen ausgetauscht werden, desweiteren setzt sich
 eine Komponente intern oft aus mehreren Klassen zusammen.
 
 #### Merkmale einer Komponente
 
- Eine Komponente exportiert eine oder mehrere Schnittstellen, dabei werden Schnittstellen als Verträge aufgefasst.
- Eine Komponente importiert andere Schnittstellen
  - Die Komponente benutzt die Methoden der importierten Schnittstelle, dabei ist die Komponente erst lauffähig, wenn alle importierten Schnittstellen zur Verfügung stehen. Die Komponente ist unabhängig von der Implementierung der importierten Schnittstellen

 
 ### Paketdiagramme

Pakete gruppieren Elemente, die einem ähnlichen Zweck dienen, und definieren Namensräume. Das Ziel des Diagramms besteht darin eine abstrakte Sicht auf das System zu ermöglichen, so dass man den Überblick behält.
Pakete können ebenfalls Pakete enthalten und Subsysteme modellieren, so dass diese in anderen Projekten wiederverwendet werden können.

![Paketdiagramme Beispiel 1](vorlesung10/Bilder/Paketdiagramm.png)

#### Notationselemente

![Paketdiagramm Notationselemente](vorlesung10/Bilder/Paketdiagramm_Notationselemente.png)

#### Assoziationen:

Beim Import kann die Sichtbarkeit der importierten Elemente und Pakete neu bestimmt werden.
- <<<import<>import>> Beziehung, die alle Namen öffentlicher Elemente eines Pakets zum importierenden Paket als öffentlich hinzufügt. Der Import ist transitiv, daher finden die importierten Namen bei einem erneuten Import von einem anderen Paket Berücksichtigung.
- <<<access<>access>> Beziehung, die alle Namen öffentlicher Elemente eines Pakets zum importierenden Paket als privat hinzufügt. Der Import ist nicht transitiv.
- <<<merge<>merge>> Nicht private Inhalte des Zielpakets werden in die Inhalte des Quellpakets verschmolzen.

### Verteilungsdiagramme

Verteilungsdiagramme dienen zur Modellierung der Laufzeitumgebung verteilter Softwaresysteme und werden parallel zu Komponentendiagrammen eingesetzt. Dargestellt werden Nodes (Rechnerknoten), auf denen Prozesse laufe, und Links (Kommunikationsbeziehungen) zwischen den Knoten.
Knoten repräsentieren Geräte, die Rechenleistung und/oder Speicher besitzen und auf verschiedene Artefakte verteilt werden:
- <<<device<>device>> Ein Gerät, das Hardware repräsentiert und Rechenkapazität besitzt
- <<<execution env<>execution env>> Eine Ausführungsumgebung, die notwendige Software repräsentiert, um das Laufzeitsystem auszuführen
- <<<executable<>executable>> Eine ausführbare Datei
- <<<artifact<>artifact>> Ein Objekt der Verteilung, zum Beispiel eine Datei

Unter Verteilung wird die Zuweisung von Artefakten an Knoten verstanden. Ein Artefakt kann dabei auf mehrere Knoten verteilt werden. Es gibt drei Notationsvarianten:
- Explizite Modellierung als Abhängigkeit mit dem Schlüsselwort <<<deploy<>deploy>>

![Verteilungsdiagramm Zuweisung 1](vorlesung10/Bilder/Zuweisung1.png)

- Grafische Schachtelung von Artefakten auf Knoten

![Verteilungsdiagramm Zuweisung 2](vorlesung10/Bilder/Zuweisung2.png)

- Notation der Artefaktnamen im Knotensymbol

![Verteilungsdiagramm Zuweisung 3](vorlesung10/Bilder/Zuweisung3.png)

Knoten können außerdem Attribute und Operationen besitzen:

![Verteilungsdiagramm Beispiel](vorlesung10/Bilder/Verteilungsdiagramm.png)

Beispiel für ein komplexeres Verteilungsdiagramm:

![Verteilungsdiagramm Beispiel 2](vorlesung10/Bilder/Verteilungsdiagramm2.png)

### Zustandsdiagramme

Zustandsdiagramme stellen das Klassenverhalten durch Zustände und Übergänge zwischen Zuständen dar. Das Verhalten hängt vom internen Zustand der Klasse ab. Zustandsdiagramme beantworten die Frage: "Wie verhält sich das System in einem bestimmten Zustand bei gewissen Ereignissen?".
