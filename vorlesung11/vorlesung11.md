# Softwareentwurf und Softwarearchitektur 

**Autoren**
Jonas Raddatz

## Lernziele

- Ziele des Softwareentwurfs erklären können
- Wissen,was eine Softwarearchitektur ist
- Bestandteile einer "guten" Softwarearchitektur kennen


## 4+1-Sichten-Softwarearchitekturmodell

 ![Softwarearchitekturmodell](vorlesung11/Bilder/softwarearchitekturmodell.png)

### 4+1-Sichten-Softwarearchitekturmodell mit UML-Diagrammen

 ![Softwarearchitekturmodell mit UML-Diagrammen](vorlesung11/Bilder/softwarearchitekturmodell_uml.png)

| Name der Sicht         | Was beschrieben wird                     | Darstellungsform                  |
| ---------------------- | ---------------------------------------- | --------------------------------- |
| Use Case Sicht         | Anwendungsfälle                          | Use Case Diagramm                 |
| logische Sicht         | Anforderungen an das System              | Paket- und Komponentendiagramme   |
| Prozess Sicht          | dynamische Aspekte des Systems, <br>Interaktion von Systemkomponenten zur Laufzeit | Interaktionsdiagramme             |
| Implementierungs Sicht | statische Eigenschaften des Systems      | Klassen- und Komponentendiagramme |
| Deployment Sicht       | physikalische Verteilung zwischen Rechnerknoten | Verteilungsdiagramm               |

## Softwareentwurf

### Einordnung in den Entwicklungsprozess

 ![Einordnung in den Entwicklungsprozess](vorlesung11/Bilder/entwicklungsprozess.png)

### Softwareentwurf

Der Softwareentwurf ist die Entwicklung einer softwaretechnischen Lösung (Softwarearchitektur) auf Basis der gegebenen Anforderungen. Anders als die rein problemorientierte Systemanalyse ist der Softwareentwurf realisierungsorientiert. Die Grenzen zwischen den beiden Schritten verlaufen jedoch fließend.

In der Entwurfsphase wird also der Übergang von der fachlichen Anforderung ("was") zu einer Realisierung/Lösungsstruktur ("wie") geschaffen.



### Tätigkeiten im Entwurfsprozess

- Um die Komplexität des Problembereichs beherrschbar zu machen, ist eine Strukturierung/Gliederung in überschaubare und handhabbare Einheiten notwendig
- Hierarchische Gliederung-> Definition einer Softwarearchitektur
- Der Softwareentwurf kann in die Bereiche Grobentwurf (Subsysteme, Schnittstellen) und Feinentwurf (Komponenten, Verfeinerung der Entwurfsklassendiagramme) aufgeteilt werden.
- Oftmals ist ein iteratives Vorgehen notwendig: ausgehend von einer ersten Gliederung wird diese verfeinert und angepasst, bis man einen stabilen Stand erreicht hat und überschaubare Einheiten entstanden sind
- Bestpractice: der Mensch kann nur Systeme überblicken, die aus wenigen Teilen (bis zu 7) bestehen. Bei mehr als 7 müssen diese Teile nacheinander betrachtet und gegliedert werden

### Softwarebausteine

| <u>Baustein</u>            | <u>Beschreibung</u>                      |
| -------------------------- | ---------------------------------------- |
| **Subsystem**              | - in sich geschlossene Einheit, funktioniert eigenständig <br>- bietet definierte Schnittstellen über Komponenten an |
| **Komponente**             | - funktional und wiederverwendbar<br>- benutzt und wird von anderen Komponenten benutzt<br>- kann aus Unterkomponenten und/oder Klasse |
| **Klasse**                 | - abstrakter "Bauplan" für Objekte       |
| **Paket**                  | - Zusammenfassung von Klassen            |
| **Modul**                  | - funktionale Einheit, die aus Operationen und Datenstrukturen besteht |
| **Bibliothek (Library)**   | - stellt eine API zur Verfügung<br>- "unsere" Software bestimmt den Kontrollfluss, indem wir die Funktionen der Bibliothek aktiv verwenden |
| **Rahmenwerk (Framework)** | - Software, in die sich "unsere" Software "einklinken" kann<br>- bestimmt den Kontrollfluss und ruft bei bestimmten Ereignissen Funktionen "unserer" Software auf |



## Softwarearchitektur

Eine Softwarearchitektur zeigt die Strukturen eines Softwaresystems auf, also Softwareteile und die Beziehungen zwischen diesen Softwareteilen. Sie ist eine abstrakte Darstellung der Lösung, bei der die Technik berücksichtigt wird (anders als bei der Systemanalyse). Zur Darstellung werden häufig Schichten verwendet.

**<u>Ziel</u>**: Vollständige Umsetzung des Analysemodells unter Berücksichtigung implementierungsspezifischer Randbedingungen

### Schichtenarchitektur

Das System wird in mehrere Schichten aufgeteilt, wobei eine Schicht logisch zusammengehörende Teile zusammenfasst. Eine Schicht stellt Dienstleistungen über Schnittstellen zur Verfügung und kann **nur** auf die direkte Vorgängerschicht zugreifen.

 ![Schichtenarchitektur](vorlesung11/Bilder/schichtenarchitektur1.png)

- Die klassische 3-Schichten-Architektur wird häufig für betriebliche Software eingesetzt


- Die Schichten können auch über verschiedene Rechnerknoten verteilt werden

 ![3-Schichtenarchitektur](vorlesung11/Bilder/schichtenarchitektur2.png)

### Azyklische Abhängigkeitsstruktur

 ![Azyklische Abhängigkeitsstruktur](vorlesung11/Bilder/azyklische_abhaengigkeitsstruktur.png)

## Entwurfsprinzipien

### Merkmale für guten Entwurf

| <u>Merkmal</u>                      | <u>Beschreibung</u>                      |
| ----------------------------------- | ---------------------------------------- |
| **Korrektheit und Vollständigkeit** | Erfüllung der funktionalen und nicht-funktionalen Anforderungen |
| **Flexibilität**                    | Softwarebausteine sind nicht  starr auf ein vorliegendes Problem angepasst, so dass Änderungen problemlos  möglich sind |
| **Wiederverwendbarkeit**            | Softwarebausteine können in neuen  Anwendungen weiterverwendet werden, sodass die Kosten für die Neuentwicklung  sinken |
| **Erweiterbarkeit**                 | System kann gut um neue Funktionalität  erweitert werden, um beispielsweise neue Bibliotheksklassen optimal  hinzuzufügen |
| **Veränderbarkeit**                 | Veränderungen an einer bestimmten  Stelle wirken sich nicht auf andere Teile des Systems aus |
| **Wartbarkeit**                     | Die Softwarebausteine sind untereinander nicht stark abhängig  voneinander, so dass es kostengünstig weiterentwickelbar ist |
| **Redundanzfreiheit**               | Keine mehrfache Verwendung von identischem Code |
| **Verständlichkeit**                | System ist logisch durch gut lesbaren  Code aufgebaut, damit Änderungen schnell und sicher umgesetzt werden können |

### Einige Entwurfsprinzipien

Es herrscht die Einsicht, dass man **vor** dem Programmieren der Software über eine gute Struktur der Software nachdenkt, um wartbare, erweiterbare Softwarebausteine zu erzeugen

**Erfahrungen zum Aufbau einer„guten“ Architektur:**

| Abkürzung | **Bedeutung**            | Beschreibung                             |
| --------- | ------------------------ | ---------------------------------------- |
| KISS      | Keep It Simple Stupid.   | Das Problem zwar vollständig und gut nachvollziehbar, aber möglichst einfach und kurz lösen |
| YAGNI     | You Ain’t Gonna Need It. | Nichts entwerfen, was erst später verwendet werden soll |
| DRY       | Don‘t repeat yourself.   | Keine Redundanzen                        |

Außerdem gilt das Prinzip "Separation of concerns", mit dem man die Ziele niedrige Kopplung und hohe Kohäsion erreicht.

#### Separation of Concerns (Trennung von Belangen)

**Concern (eng. für Belang)**: Gesichtspunkt, der in einem Software-System behandelt werden muss, um die übergreifenden Systemziele zu erreichen.

Das Prinzip Seperation of concerns besagt, dass unterschiedliche Belange auch durch unterschiedliche Systemteile behandelt werden sollen. Dazu sollten verschiedene Elemente der Aufgabe möglichst in verschiedene Elemente der Lösung unterteilt werden

 ![Separation of Concerns](vorlesung11/Bilder/separationofconcerns.png)

#### Kohäsion und Kopplung

Insgesamt sind eine hohe Kohäsion und niedrige Kopplung anzustreben.  Dadurch können Subsysteme  relativ einfach ausgetauscht bzw. verändert und die Auswirkungen lokal begrenzt werden.

##### Hohe Kohäsion (Zusammenhalt):

Die Dinge (Klassen) sollen in Struktureinheiten zusammengefasst werden, die inhaltlich zusammengehören. Die Klassen innerhalb einer solchen Struktureinheit haben intern eine hohe Abhängigkeit und bearbeiten gemeinsam ein Thema.

![Kohäsion](vorlesung11/Bilder/kohaesion.png)

**Hohe Kohäsion erleichtert Verständnis, Wartung und Anpassung!**

##### Niedrige Kopplung (Abhängigkeiten):

Einzelne Struktureinheiten sollen möglichst unabhängig voneinander sein. Änderungen an einer Komponente sollten wenig und einfache Änderungen in einer anderen Komponente nach sich ziehen.

![Hohe Kopplung](vorlesung11/Bilder/hohe_kopplung.png)

![Niedrige Kopplung](vorlesung11/Bilder/niedrige_kopplung.png)

**Geringe Kopplung erleichtert die Wartbarkeit!**

## Entwurfsfehler

Wie in allen Schritten des Entwicklungsprozesses werden auch beim Softwareentwurf Fehler gemacht. Oft gemachte Entwurfsfehler sind sogenannte „Anti-Patterns“ und in der Implementierung existieren im Source-Code sogenannte "Üble Gerüche" (Bad Smells). Metriken helfen die beiden Fehlertypen zu finden.

Bad Smells und Anti-Patterns sind meistens ein Signal zum Refaktorisieren des Source-Codes.

![Entwurfsfehler](vorlesung11/Bilder/entwurfsfehler.png)

### Anti Pattern

Unter einem Anti Pattern versteht man einen schlechten Lösungsansatz für ein bestimmtes Problem. Häufig ist es eine Lösung, die mehr Probleme einführt als löst.

Nur wenn man Anti-Patterns kennt und versteht, kann man sie vermeiden oder die Lösung verbessern. Antipatterns können dann lehrreicher sein als Patterns.

| Beispiel              | Beschreibung                             |
| --------------------- | ---------------------------------------- |
| Lava Fluss            | "Dead Code" = Code, um den herum programmiert wird |
| Copy and Paste        | kopierter Code, unnötige Redundanz       |
| Blob                  | Eine große Klasse mit vielen Methoden und Attributen dominiert den Ablauf |
| Poltergeist           | Unnötige Klassen mit winzigen Aufgaben   |
| Funktionale Zerlegung | Abfolge von Funktionen auf objektorientierte Sprache übertragen |

## Zusammenfassung

- Merkmale guter Entwürfe
  - Einfachheit ("KISS - Keep It Stupid Simple")
  - Geheimnisprinzip
  - Niedrige Kopplung zwischen Klassen/Paketen/Subsystemen
  - Hohe Bindung (Kohäsion) zwischen Klassen/Paketen/Subsystemen
- Rad nicht neu erfinden, sondern Wiederverwendung und Erweiterbarkeit beim Entwurf "einplanen"
- Für den Entwurf von Software-Architekturen ist viel Erfahrung notwendig.
- Die Kenntnis von Anti-Patterns hilft, diese zu vermeiden, zu erkennen und zu beseitigen