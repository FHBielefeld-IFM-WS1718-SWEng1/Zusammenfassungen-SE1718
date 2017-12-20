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
