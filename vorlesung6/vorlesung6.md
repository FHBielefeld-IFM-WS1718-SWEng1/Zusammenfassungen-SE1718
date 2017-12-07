## Anforderungsanalyse mit UML-Use Case Diagramm, Satzschablone und textueller Use Case Definition

**Autoren**:
Florian B., Florian W.

### Lernziele
- Verstehen, was Anforderungen sind
- Erklären können, was für unterschiedliche Anforderungsarten es gibt
- Verstehen, wie Anforderungen definiert werden
- Den Prozess der Anforderungsdefinition erklären können
- Use Case Diagramme modellieren können
- Verstehen, wie Anforderungen mit Satzschablonen formuliert werden
- Verstehen, wie textuelle Use Case Definitionen spezifiziert werden

### Einordnung in den Entwicklungsprozess

![Einordnung in den Entwicklungsprozess](vorlesung6/bilder/Bild1.png)
#### Stakeholder
Der Stakeholder ist eine wichtige Quelle für Informationen. Dieser hat direkten oder indirekten Einfluss auf die Anforderungen des Systems. Wenn man bei den Anforderungen einen Stakeholder weglässt, kann das dazu führen, dass es Lücken im System gibt. Ein paar wichtige Stakeholder: Kunde, Mitarbeiter, Eigentümer, Zulieferer und andere Dienstleister. 

![Stakeholder](vorlesung6/bilder/Bild2.png)

#### Arten von Anforderungsdefinitionen

- Nutzeranforderung -------------------------------------- Lastenheft
	Die Nutzeranforderung, die im Lastenheft steht, beschreibt was der Nutzer oder Kunde haben will. 

- Systemanforderung --------------------------------------Pflichtenheft
	Das Pflichtenheft ist aus der Sicht desjenigen geschrieben, der das System realisiert. Also ist dieses etwas technischer und präziser. 

#### Hinweise zu Art und Inhalt von Dokumenten in einem Softwareprojekt

Das Lasten- und Pflichtenheft sind eine Möglichkeit der Dokumentation. In der Praxis werden allerdings auch andere Dokumentenarten erzeugt. In größeren Projekten mit vielen Menschen ist das sogar notwendig. 

#### Anforderungsanalyse ist ein systematischer Ansatz

In der Anforderungsanalyse ermittelt man die Anforderungen an ein System. Man setzt außerdem die Verträge zwischen IT-Dienstleister und dem Kunden fest. Es dient zur Herstellung der Prüfbarkeit eines Systems gegenüber dem Kunden. 

#### Ziele des Requirement Engineering

Man sollte dem Auftraggeber beim Erstellen dieser Anforderungen unterstützen. Dem Anforderungsanalytiker sollte man ebenfalls bei der Aufbereitung unter die Arme greifen.
	- Formulieren, Klassifizieren, Hierachisieren, Priorisieren

### Was sind Anforderungen? 

- Legen qualitative und quantitative Eigenschaften vom Softwareprojekt fest

#### Was beschreiben Anforderungen

Anforderungen beschreiben die Bedingungen, die man zum Lösen eines Problems einhalten soll. Ebenfalls die Bedingungen, die ein System oder eine Systemkomponente erfüllen muss, beschreibt diese Anforderung. Also: Die Anforderungsbeschreibung legt fest was was ein Produkt können soll/muss.


### Wege zur Anforderug

Um die Anforderungen herauszufinden ist eine Befragung von zentralen Stakeholdern sinnvoll. Man kann auch Interviews führen, alte Systeme analysieren oder sich Dokumente von Kunden ansehen. 

### Arten von Anforderungen
- Funktionale Anforderungen: Was soll das System können
- Nicht funktionale Anforderungen: Welche Eigenschaften soll das System neben der Funktionalität aufweisen

![Arten von Anforerungen](vorlesung6/bilder/Bild3.png)

| Funktionale Anforderungen | Nicht funktionale Anforderungen |
|--------|--------|
| Funktionaliäten|   Leistungsanforderungen     |
|Daten | Qualitätsanforderungen |
|Schnittstellen | Realisierungsanforderungen | 


	
![Nicht Funktionale Anforderungen](vorlesung6/bilder/Bild4.png)

### Probleme bei der Anforderungsanalyse

![Arten von Anforerungen](vorlesung6/bilder/Bild5.png)

Ein großes Problem ist, dass der Kunde eigentlich gar nicht weiß was er eigentlich will. Und diese Anforderungen, die dabei herauskommen, kann man nicht maschinell bearbeiten, also muss man diese per Hand durchgehen. Die unterschiedlichen Leute, die beteiligt sind, haben oft unterschiedliche Ansprüche an das System. Dadruch gibt es widersprüchliche Aussagen. Diese müssen das zusätzlich noch erkannt werden. 
Anforderungen können sich auch noch während des Prozesses ändern. Experten lassen auch gerne mal ein paar Dinge aus, die für Sie offensichtlich ist. Wenn es Konflikte gibt muss es keine klaren Entscheidungen geben. 

|Anforderungen sind: | Beispiele |
|--------|--------|
|   mehrdeutig     |   ein Fahrrad wie Klaus    |
| nicht erfüllbar | Sandmännchen kennenlernen |
| überbestimmt  | ein runder Ball | 
| inkonsistent | ein schnelles Auto, ein Oldtimer|
|unvollständig| 

### Vorgehensweise beim Requirements engineering

![Bild6](vorlesung6/bilder/Bild6.png)
![Bild7](vorlesung6/bilder/Bild7.png)

#### Use Case Satzschablone

Hier präzisiert man die natürlichsprachigen Anforderungen. Die Anforderungen des Kunden werden eindeutig und konsistent formuliert.

#### Textuelle Use Case Definition

Die Beschreibung der Arbeitsabläufe ist natürlichsprachig. Man beschreibt Interaktionen von Akteuren mit einem System. Häufig ergänzt man hierzu noch Zustands- und Aktivitätsdiagramme

#### Use Case Diagramme


Zeigt das Verhalten des Sytems gegebenüber Akteuren. Stellt außerdem die Abhängigkeiten zwischen den Anwendungsfällen dar.

### Satzschablonen für die Anforderungsermittlung

![Bild8](vorlesung6/bilder/Bild8.png)

#### Charakterisierung von Systemaktivitäten

1. Selbstständige Systemaktivität
	- Das System führt den Prozess selbstständig durch

2. Benutzerinteraktion
	- Das System stellt dem Nutzer die Prozessfunktionalität zur Verfügung 

3. Schnittstellenanforderung 
	- Das System wird mit externen Programmen ausgeführt

#### Satzschablone mit Rupp

- Standardisierte Normsprache
- Hilft Anforderungen aufzunehmen und zu formulieren

![Bild9](vorlesung6/bilder/Bild9.png)

##### Beispiele:
- 	Nach der Kontaktaufnahme durch die Software „Globalview“ muss das System fähig sein, Anfragen nach den Projektnamen, deren Gesamtaufwänden und Fertigstellungsgraden anzunehmen.
- Das Personalmodul wird fähig sein, Personendaten aus der Datenbank zu importieren
![Bild10](vorlesung6/bilder/Bild10.png)
![Bild11](vorlesung6/bilder/Bild11.png)
![Bild12](vorlesung6/bilder/Bild12.png)Bedigung Bedigung Bedigung
![Bild13](vorlesung6/bilder/Bild13.png)

### Use Case (Anwendungsfall)

Ein Use Case definiert die funktionalen Hauptaufgaben eines Systems.
In der Sprache der Stakeholder beschreibt ein Use Case eine konsistente und zielgerichtete Interaktion zwischen Benutzer und System.
Aus der Sicht des Anwenders beschreibt ein Use Case das gewünschte Systemverhalten und Anforderungen, die das System erfüllen soll.
Außerdem wird beschrieben, was das System leisten muss, aber nicht, wie es dies leisten soll.
Um ein Ziel bzw. gewünschtes Ergebnis zu erreichen, führt ein Akteur mehrere zusammenhängende Aufgaben durch.
Alle Anwendungsfälle zusammen dokumentieren die Möglichkeiten der Benutzung des Softwaresystems und werden in einem Use Case Diagramm dargestellt.

### Use Case vs. User Story

- User Story
  - einfache kurze Beschreibung eines Benutzerziels, um einen Nutzen zu generieren
  - eignen sich für inkrementelles Vorgehen
  - als Basis, um über Anforderungen zu reden
  - werden als Planungsinstrument eingesetzt und so lange kompakt „kleingeschnitten“, bis sie in einem festgelegten Zeitraum einer Iteration umgesetzt werden können


- Use Case
  - detaillierte Spezifikation von Funktionalität (Reihenfolge von Systemaktivitäten), um ein gewünschtes Resultat zu erzielen
  - fokussieren auf Nutzerinteraktionen mit einem System, so dass das Ziel dem Nutzer klar wird
  - enthalten include- und extends-Beziehungen
  - eignen sich gut für eine Neuentwicklung
  - als Instrument zur Dokumentation eingesetzt

-----------------------------------------------------------------------------------------------------------------

### Szenario

- Szenario
  - konkrete Ausprägung eines Anwendungsfalls
  - ein möglicher Ablauf mit konkreten Werten
  - ist eine Instanz eines Anwendungsfalls
  - Beschreibungen des Systems, wie es in der Praxis benutzt wird
  - hilfreich bei der Anforderungsermittlung, da Personen diese besser verstehen als abstrakte Angaben
  - können durch Interaktionsdiagramme (Sequenzdiagramm, Kommunikationsdiagramm) dargestellt werden

- Ein Szenario beschreibt eine Abfolge von Schritten, die vom Use Case zu durchlaufen sind. Diese Abläufe werden in Use Case Definitionen detailliert modelliert
  - Normalabläufen, normaler/erfolgreicher Ablauf
  - Alternativabläufe, andere Wege zum Ziel als bei Normalabläufe
  - führen nicht zum Ziel, z.B. infolge eines "fachlichen Fehlers" oder bei einem Abbruch durch den Akteur
 
- Anwendungsfall
  - beschreibt eine abstrakte Interaktion zwischen Akteuren und dem System
  - können mehrere Szenarien existieren

![Vor gehensweise beim  Requirements Engineering](vorlesung6/bilder/bbild1.png "Vorgehensweise beim  Requirements Engineering")

-----------------------------------------------------------------------------------------------------------------

### Textuelle Use Case Definition 

![Schablone zur textuellen Definition von Use Cases](vorlesung6/bilder/bbild2.png "Schablone zur textuellen Definition von Use Cases")

#### Definition des Ablaufs:

- In der Zeile „Ablauf“ steht der ganze Ablauf des Use Cases mit allen möglichen Ausnahmen und/oder Varianten
- Dies sind die Szenarien
- wird in Schritte unterteilt und jeder Schritt fortlaufend nummeriert
- eine Ausnahme oder Variante wird unter alternativen Abläufen erwähnt
- die Nummer des Schrittes wird vom Ablauf unverändert übernommen und hinter der Nummer alphabetisch weiter nummeriert
- Ein einzelner Schritt beginnt immer mit der Nennung des Aktors

![Definition des Ablaufs](vorlesung6/bilder/bbild3.png "Definition des Ablaufs")

![Definition des Ablaufs2](vorlesung6/bilder/bbild4.png "Definition des Ablaufs2")

![Definition des Ablaufs3](vorlesung6/bilder/bbild5.png "Definition des Ablaufs3")

![Definition des Ablaufs4](vorlesung6/bilder/bbild6.png "Definition des Ablaufs4")

-----------------------------------------------------------------------------------------------------------------

### Notationselemente für Use Case Diagramme

![UML](vorlesung6/bilder/bbild7.png "UML")

- Achtung: „Kunde nicht gefunden“ kein geeigneter Use Case
- UC-Name wie „Kundendaten einsehen“ immer in den Use Case schreiben

#### Was ist ein Akteur (Aktor)?

- Rolle, die ein Benutzer des Systems spielt
- Häufig eine Person
- Kann auch Organisationseinheit oder anderes System sein
- Befindet sich immer außerhalb des Systems
- Aktoren können in der Regel aus der Menge der Stakeholder entnommen werden.

Notation:

![Notation](vorlesung6/bilder/nota.png "Notation")

#### Arten von Aktoren

- Menschlich
  - z.B. Anfänger, geübter Benutzer, Admin
- Nicht-menschlich
  - z.B. Messaging-System, E-Mail-System
- Primär: Hauptnutzer der Anwendung
- Sekundär: notwendig für das Funktionieren des Systems
- Aktiv: stößt selbst Anwendungsfälle an
- Passiv: stößt selbst keine Anwendungsfälle an

Beispiel:

![beispiel](vorlesung6/bilder/beispiel.png "beispiel")

![UML2](vorlesung6/bilder/bbild8.png "UML2")

![UML3](vorlesung6/bilder/bbild9.png "UML3")

#### Vererbung bei Akteuren und Kardinalitäten

![Vererbung](vorlesung6/bilder/bbild10.png "Vererbung")

#### Use-Case-Diagramm – Generalisierung

![DIA](vorlesung6/bilder/bbild11.png "DIA")

#### Use-Case-Diagramm – <<include>> Beziehung

![bild12](vorlesung6/bbild12.png "bild12")

- Die «include»-Beziehung visualisiert, dass ein Use-Case (A) das Verhalten eines anderen Use-Case (B) importiert. Die Beziehung ist nicht optional, so dass  das Verhalten immer importiert wird.
- Erst die Beschreibung der Aktionen definiert, an welcher Stelle der Use-Case B inkludiert wird.

#### Use-Case-Diagramm – <<extend>> Beziehung

![bild13](vorlesung6/bbild13.png "bild13")

- Die «extend»-Beziehung zeigt an, dass das Verhalten eines Use-Case (A) durch einen anderen Use-Case (B) erweitert werden kann, aber nicht muss.
- Den Zeitpunkt, an dem ein Verhalten eines Use-Case erweitert werden kann, bezeichnet man als Erweiterungspunkt (engl. extension point). 
- Ein Use-Case darf mehrere Erweiterungspunkte besitzen.
- Eine Erweiterung kann noch um eine optionale Bedingung ergänzt werden.
  - wenn die Bedingung erfüllt ist, wird die Erweiterung tatsächlich ausgeführt

![bild14](vorlesung6/bbild14.png "bild14")

![bild15](vorlesung6/bbild15.png "bild15")

![bild16](vorlesung6/bbild16.png "bild16")

-----------------------------------------------------------------------------------------------------------------

### Best Practices

#### Best  Practice  Use  Cases

- für den Use Case eine sinnvolle Bezeichnung wählen, die aus einem Substantiv und einem aktiven Verb bestehen muss. Beispiele: „Antrag erfassen“, „Report drucken“, „Spiel starten“
- Konsistenz in der Sprache, standardisierte Sprache im Use Case
- Nicht „User Case“, sondern „Use Case“
- Keine Abläufe modellieren
  - jeder Use Case enthält selbst einen abgeschlossenen Ablauf
- Keine Datenflüsse modellieren
  - wenn „Auftrag anlegen“ und „Auftrag genehmigen“ zu verschiedenen Zeiten und von verschiedenen Personen durchgeführt werden, wird im Use Case-Diagramm keine Beziehung gezeichnet
- Aktor immer außerhalb des Systems darstellen
- Kein unterschiedlichen Aktoren mit Zustand (z.B. Benutzer & Registrierter Benutzer)
- Keine nicht-funktionalen Use Cases modellieren
- Use Case-Diagramme nicht zu umfangreich
  - gruppieren verwandter Use Cases in einer Use Case Gruppe und modellieren mehrerer Use Case Diagramme 
- Wenn das Use Case Diagramm einen zentralen Use Case zeigt, auf den viele andere mit Beziehungen wie „include“, „extends“ oder Generalisierung zeigen, ist dies ein Hinweis auf eine Use Case Gruppe
- Keine Screenflows mit allen Möglichkeiten modellieren
- Auf die wichtigsten include- und extend-Beziehungen konzentrieren
- Große Use Case-Diagramme in mehrere Diagramme aufteilen
- Use Case mit mehreren Akteuren
  - Hat ein Use Case mehrere Akteure, so führen diese ihn gemeinsam aus
  - Soll ein Use Case von unterschiedlichen Akteuren jeweils alleine ausgeführt werden, so erstellt man einen generalisierten Akteur.

#### Best practice: Funktionale Größe eines Use Cases

- keine Vorschriften, wie umfangreich ein Use Case sein soll
- Use Case so abstrakt wie möglich und so konkret wie nötig
- Use Cases eignen sich nicht zur funktionalen Zerlegung
  - ein Use Case beschreibt keine einzelnen Schritte, Operationen oder Transaktionen (beispielsweise "Vertrag drucken", "Kunden-Nr. erzeugen" etc.), sondern relativ große Abläufe (bspw. "Neuen Kunden aufnehmen")
  - „Name eingeben“ oder „Start drücken“ sind zu klein, da es keine abgeschlossenen Aufgaben sind. „Dienstfahrzeug beschaffen“ ist zu groß, da mehrere Use Cases erforderlich sind (beantragen, genehmigen, Bestellung aufgeben …)
- „Kunde anlegen“, „Kunde ändern“ und „Kunde löschen“ als drei Use Cases modellieren oder genügt ein Use Case „Kunde bearbeiten“?
  - hängt davon ab, ob es große Unterschiede zwischen den einzelnen Use Cases gibt, z. B. umfangreiche Prüfungen beim Anlegen, die beim Bearbeiten wegfallen
  - hängt davon ab, ob es sehr viele Use Cases gibt und das Diagramm unübersichtlich wird



