## Agile Vorgehensmodelle (XP, Scrum, Kanban)
### Lernziele
- die agilen Vorgehensmodelle kennenlernen
- User Stories und Mockups

### Xtreme Programming (XP)

Xtreme Programming ist ein leichtgewichtiges Vorgehensmodell, welches auf der Entwicklung und Auslieferung sehr kleiner Inkremente basiert. Die Entwicklung von XP wurde von zwei Forderungen motiviert:
- Develop for today
	- Konzentration auf aktuelle Probleme
- Do the simplest thing that could possible work. (KISS-Prinzip: Keep it simple, stupid)
	- Verwendung des einfachsten Entwurfs

![Vorgehensmodelle](vorlesung3/bilder/Bild2.png "Vorgehensmodelle im Vergleich")

#### XP Paarprogrammierung
- alle Programmiertätigkeiten werden im Paar ausgeführt
	- Rollenverteilung Fahrer und Beifahrer
		- Fahrer denkt an Implementierung der Programm-Logik
		- Beifahrer denkt strategisch, führt ständige Durchsicht durch
- führt zu höherer Qualität

#### XP-Ablauf

![XP-Ablauf](vorlesung3/bilder/Bild4.png "XP-Ablauf")

### "Test first" und Test-driven-development (TDD)
Die Tests werden vor der Implementierung "gegen" ein Interface geschrieben, wodurch Lücken in der Spezifikation besser erkennbar sind. Tests werden aus den User Stories  schrittweise entwickelt und zudem werden Kunden in die Testentwicklung und Validierung einbezogen.
- Unterstützt Refactoring
- Kompensation für fehlende Entwurfsphase
- Testautomatisierung

![TDD](vorlesung3/bilder/Bild3.png "Test-driven-development (TDD)")

### Scrum
"Scrum": Gedränge beim Rugby

![Scrum](vorlesung3/bilder/Bild5.png "Scrum")

| Rollen | Meetings | Artefakte |
|--------|--------|--------|
|    Produkt-Owner    |    Sprint-Planung    |    Product Backlog   |
|    Scrum-Master    |    Sprint-Review    |    Sprint Backlog    |
|    Scrum-Team    |    Sprint-Retrospektive    |    Burndown-Diagramm    |
|      |    Tägliches Scrum-Meeting    |      |

#### Scrum Rollen

##### Product-Owner (Auftraggeber)
Dieser legt die Anforderungen sowie den Auslieferungstermin fest. Zudem pflegt er das Product-Backlog und das Budget zur Verfügung und akzeptiert beziehungsweise lehnt Arbeitsergebnisse ab. Weiterhin priorisiert er die Anforderungen und passt diese an.

##### Scrum-Master
Der Scrum-Master stellt die Einhaltung der Scrum-Werte und -Techniken sicher. Er sorgt dafür, dass das Entwicklungsteam funktional und produktiv ist und schützt das Entwicklungsteam vor äußeren Störungen. Zudem versucht er das Team anzustoßen, bei der Vorbereitung zu helfen und diverse Hindernisse zu beseitigen. Dazu unterstützt der Scrum-Master die Zusammenarbeit zwischen allen Rollen.

##### Scrum-Team (Entwicklungsteam)
Das Scrum-Team besteht aus 5 bis 9 Personen mit unterschiedlichen Fachgebieten die sich untereinander selbst organisieren und eigenständig Aufgaben übernehmen.

#### Scrum Artefakte

##### Product Backlog (Anforderungsliste)
Das Product Backlog enthält eine Liste mit allen gewünschten funktionalen und nicht-funktionalen Produktanforderungen (zum Beispiel als User Stories). Jeder Eintrag soll wertvoll für Benutzer oder Kunden des Produktes sein. Der Produkt-Owner priorisiert das Product Backlog, wobei höher priorisierte Einträge detaillierter dargestellt werden. Jeder hat Zugriff auf das Product Backlog und kann Einträge beisteuern. Zudem enthält die Anforderungsliste auch alle Projektarbeiten (z.b Tests von Technologien oder die Entwicklung von Prototypen).

##### User Stories
Diese sollen helfen über Anforderungen zu reden. Sie enthalten keine Details über die Implementierung sondern nur "Wer - Was - Warum" in einem Satz. Sowohl Benutzer als auch Entwickler können User Stories schreiben.
- Schablone: Als "Nutzer-Rolle" möchte ich "Ziel/Wunsch", so dass ich "Nutzen/Wert".
	- Beispiel: Als Benutzer möchte ich detaillierte Infos zu den Veränderungen meiner Twitter-Follower haben, so dass ich mein weiteres Verhalten daran ausrichten kann.

##### Akzeptanzkriterien
Aus den User Stories können dann Akzeptanzkriterien abgeleitet werden.
- Beispiel für Akzeptanzkriterien:
	- Der Name eines Users wird mit einem Link auf ihr Profil bei Twitter versehen

##### Priorisierung für User Stories
User Stories können nach Zielen oder nach der MoSCow-Methode (Geschäftswert) oder gemäß Kano-Analyse (Kundenwünsche) priorisiert werden.
- Ziele:
	- KANN: Das Erreichen dieser Wunschziele stellt einen zusätzlichen Bonus dar
	- SOLL: Bringen die Gesamtaufgabe nicht zum scheitern, aber beeinträchtigen die Zufriedenheit mit dem Ergebnis
	- MUSS: Werden diese Ziele nicht erreicht, gilt die Aufgabe als gescheitert.
- MoSCoW:
	- MUST bezeichnet Anforderungen, die für die Aufgabe essentiell wichtig und nicht verhandelbar sind. Eine ausbleibende Umsetzung würde zum Scheitern der Aufgabe führen.
	- SHOULD sind Anforderungen, die zwar nicht erfolgskritisch für die Aufgabe sind, aber denoch eine hohe Relevanz besitzen.
	- COULD bezeichnet Anforderungen die eine geringe Relevanz haben und oft als "nice to have" bezeichnet werden. Sie werden erst berücksichtigt wenn neben der Bearbeitung von MUST und SHOULD noch Kapazitäten vorhanden sind.
	- WON'T sind Anforderungen die aktuell nicht relevant sind oder eine sehr geringe Priorität haben. Diese Anforderungen könnten zu einem anderen Zeitpunkt wichtig sein. Sie sollten kontinuierlich neu bewertet werden.

![Scrum](vorlesung3/bilder/Bild6.png "Scrum")

#### Wireframes/ GUI Mockups

Ein Wireframe oder eine GUI Mockup ist ein skizzenähnlicher Entwurf der grafischen Benutzeroberfläche. Dabei unterscheidet man zwischen:
- Wireframes:
	- Beim Wireframe fügt man keine Bilder und keine Farben ein.
- Mockup:
	- Kann detailliertere Darstellungen mit Bildern enthalten, die auch Farbe enthalten können.
	- Diese Mockups können auch durch Mockup_Werkzeuge programmiert werden und dadurch interaktiv sein.

#### DoR(Definition of Ready)
- Ziel und akzeptanzkriterien sind gegeben
- Story ist geschätz
- Story ist nicht zu umfangreich
- Abhängigkeiten und Schnittstellen sind bekannte und geplant
- Es ist bekannt wer was zu tun hat

#### DoD(Definition of Done)
- Unit Test sind vorhanden
- Peer Review(Qualitätssicherung mit unabhängigem Gutachter aus selber Gebiet)
- Die Software ist in der Entwicklungsumgebung "deployed"(fertig) und es gibt einen Build(mobile Anwendung zur Installation auf anderen Systemen)

#### Sprint Backlog(Aufgabenliste)
Die Aufgabenliste dient zur Detailplanung eines Sprints(Periode in der eine Aufgabe erledigt sein muss) und enthält alle Aufgaben, die zur Erfüllung des Ziels notwendig sind. Dabei entscheidet das Team zu was sie sich in der Implentierung verpflichten können. Der Produkt-Owner kann bei Fragen gefragt werden. Die Aufgaben werden zusammen im Aufwand identifiziert und geschätzt. Die Entwickler suchen sich ihre Aufgaben selbst aus. Es wird nicht zugegewiesen! Jedes Mitglied kann hierbei Taks hinzunehmen, löschen oder ändern. 

#### Burndown Chart(Restaufwandsdiagramm)

Das Burndown Chart zeigt den Fortschritt des Sprints an, indem es den noch zu erbringenden Restaufwand und schon geleistete Arbeit gegenüber stellt. Dieses Diagramm wird täglich, für den besseren Überblick,aktualisiert.

![BurnboardChart](vorlesung3/bilder/Bild7.png "Burndown Chart")

Das Scrum Board zeigt dabei was noch zu tun ist, was momentan ausgeführt ist und was schon fertig ist. 

![ScrumBoard](vorlesung3/bilder/Bild8.png "Scrum Board")

### Scrum Meetings

#### Sprintplanung
- Das Team erstellt zusammen mit dem Scrum Master die Aufgabeliste, indem es Anforderungen und Produktanforderungen auswählt, die es im Sprint erledigen kann. 
- Die Tasks werden bestimmt und in der Zeit geschätzt. Dabei sind 1-16 Stunden üblich.

#### Schätztechniken

Man muss dabei Artefakte(Also z.B. ein Task) innerhalb des Sprint-Backlogs schätzen. Die Einheit dafür sind abstakte, vergleichende Story Punkte. Um das ganze zu verbessern, muss jedes Mitglied schätzen und von diesen Schätzungen wird ein Mittelwert gebildet. 

| Punktwert | Semantik |
|--------|--------|--------|
|    0    |   Kein Aufwand  |
|	1	|	Sehr kleiner Aufwand |
|2| kleienr Aufwand:doppelt so groß wie 1|
|3|mittlerer Aufwand:so groß wie 1 + 2|
|5| Großer Aufwand: so groß wie 2 + 3|
|8| Sehr großer Aufwand: so groß wie 5 + 3|
|13| Riesiger Aufwand: So groß wie 8 + 5|

#### Daily Scrum(Tägliches Scrum Treffen)
- Parameter
	- Täglich, Gleicher Ort, gleiche Zeit, <15 Minuten, Stand-Up
- Jedes Mitglied beantwortet folgende Fragen:
	-  Was hast du seit dem letzen Mal geschafft
	-  Was willst du bis zum nächsten Mal tun
	-  Was behindert dich beim Vorwärtskommen
- Dabei sollen keine Probleme gelöst werden, sondern nur das Team aufeinander abgestimmt werden
- Das heißt, dass man keine Statusberichte für den Scrum Master macht, sondern nur den Kollegen Informationen für die Abstimmung gibt
- Falls Diskussionen anfallen, werden diese nach dem Meeting geklärt
- Es dürfen alle teilnehmen, aber es dürfen nur Mitglieder und der Scrum Master sprechen. 
- Hindernisliste wird ggf. aufgeüllt

#### Sprint 
- Serien von Sprints sorgen für iteratives Vorankommen
- Ein Sprint dauert typischerweise maximal 30 Tage
- Das Produkt wird während des Sprints entworden, kodiert und gestestet
- Am Ende steht ein auslieferbares Produkt

![Sprint](vorlesung3/bilder/Bild8.png "Sprint")


#### Sprint-Review-Treffen
- Das Entwicklungsteam stellt die neuen Ergebnisse vor, indem es die neuen Funktionen demonstiert
- Keine Folien, sondern Softwaredemo
- Das Team präsentiert, was es erreicht hat
- Product Owner und andere geben Feedback

#### Sprint-Retrospektive
- Der letze Sprint wird analysiert
- Entwicklungsteam, Scrum-Master, der Auftraggeber und vielleicht auch der Endkunde nehmen teil. 
- Was lief gut? 
- Was kann verbessert werden? 
- Diskussion der identifizierten Probleme

### Kanban

#### Was ist Kanban? 

- Ursprünglich aus em Produktionsbereich von Toyota
- Ziel: Reduzierung der Lagerbestände druch Finden des Optimalen Arbeitsflusses. ("Just in Time Produktion")
- Ist ein agiles Vorgehensmodell in der Softwareentwicklung
- Wenig Komplexität und hohe Flexibilität
- Stetige Verbesserung
- Fördert Transparenz und Kommunikation im Team
- Beruht darauf, dass nicht vorgeschrieben ist wie etwas getan werden muss, sondern nur, dass es getan werden muss. 
- Kein Push- sondern Pull Prinzip
	- Nur das benötigt wird produzieren. Und auch nur wenn es benötigt wird.
	- Mitarbeiter wählen Aufgaben selbst

#### Die Sechs Kernpraktiken von Kanban
1. Mache Arbeit sichtbar
2. Limitiere den Work-in-Progress (WiP)
3. Kontrolliere den Arbeitsfluss
4. Mache die Prozessregeln explizit
5. Implementiere Feedback-Mechanismen
6. Führe gemeinschaftliche Verbesserung durch

#### 1: Mache Arbeit sichtbar
Durch eine Darstellung des gesamten Prozesses am Kanban-Board hat jeder den kompletten Überblick. Durch die Darstellung werden auch Fehler, Problemquellen und Engpässe leichter erkannt.
![Zeichnung](vorlesung3/bilder/KanbanBoard.png "KanbanBoard")
Probleme beim Release legen den ganzen Betrieb lahm, wodurch es oft besser ist, erst den Engpass zu beheben und dann den Betrieb fortzusetzen.
![Zeichnung](vorlesung3/bilder/KanbanBoardReleaseProblem.png "KanbanBoard")

#### 2: Limitiere den Work-in-Progress (WiP)
Menschen sind nicht multitaskingfähig und aufgrund dessen benötigt das Wechseln zwischen Tätigkeiten Einarbeitungsaufwand.
![Zeichnung](vorlesung3/bilder/SequentielleVSParilder.png "Sequentielle vs parallele Arbeit")
Parallele Arbeit ist langsamer, jedoch geht es erfahrungsgemäß nicht ohne Parallelität. Daher sollte man seine parallelen Tätigkeiten limitieren. Somit gilt : Ist das Limit erreicht, wird keine weitere Aufgabe angefangen. Daraus folgt, dass die Effizienz steigt, man eine bessere Übersicht hat und man weniger Überlastet ist.

#### 3: Kontrolliere den Arbeitsfluss
Das größte Problem, welches den Arbeitsfluss stören kann, ist ein Engpass. Also versucht man diese zu vermeiden. Dies erreicht man dadruch, dass man seine Aufgaben in Arbeitstypen und Serviceklassen aufteilt.
- Arbeitstypen: Art der Tätigkeit
- Serviceklasse: Klassifizierung der Arbeit aufgrund der Auswirkung auf das Geschäft

Unter Arbeitstypen versteht man zum Beispiel neue Features schreiben, Bugfixes schreiben oder Wartungsarbeiten machen.
Serviceklassen entscheidet man danach, ob die Aufgabe eine Standardaufgabe ist oder es einen festen Liefertermin gibt oder ob die Priorität höher ist als andere.

#### 4: Mache die Prozessregeln explizit
Kanban selbst gibt nur wenig Regeln vor, wodurch das Team Regeln bestimmt, die für jeden einsehbar sind.
Bespiel:
- "Definition of Done" (ähnlich Scrum)
- Was genau bedeuten die einzelnen Spalten?

#### 5: Implementiere Feedback-Mechanismen
Das Ziel von Kanban ist die kontinuierliche Verbesserung durch die Kommunikation der Mitarbeiter. (Schwächen erkennen, Probleme diskutieren, Änderung beschließen)
Dafür gibt es zum einen das "Daily Standup Meeting" in dem sich das Team täglich trifft, um den Fortschritt zu besprechen.
Des Weiteren gibt die Retrospektive (analog zu Scrum) in der eine ausführliche Besprechung in größeren Abständen stattfindet.
Außerdem gibt es noch Operation Reviews, welche zur Besprechung mit Leuten aus anderen Abteilungen dient. Dies hilft dem Team einen genrellen Überblick zu kriegen.

#### 6: Führe gemeinschaftliche Verbesserung durch
Problemvermeidung im Betriebsverlauf wird lange erforscht und oft ist es sinnvoll auf bewährte Lösung zu setzen.

#### Kanban und Scrum: Gemeinsamkeiten
- agil und schlank
- Transparent
- fördern Kommunikation und Selbstorganisation
- brechen Aufgaben in Teilaufgaben auf
- setzen auf inkrementelle Verbesserung

#### Kanban und Scrum: Unterschiede
![Zeichen](vorlesung3/bilder/KanbanScrumUnterschiede.png "Unterschiede")

#### Kanban oder Scrum?
Vorteile von Scrum
- feste Rollenverteilung -> Routine
- in größeren Gruppen einsetzbar

Vorteile von Kanban
- mehr Freiheit und weniger Bürokratie
- keine festen Meeting-Zeiten

#### Zusammenfassung
- Agile Vorgehensmodelle wie Scrum, XP und Kanban sollen die Softwarequalität erhöhen
- Aus XP entstammen die Praktiken Pairprogramming und „Test First“
- Scrum besteht aus den drei Konzepten „Rollen“, „Artefakte“, „Meetings“
- Bei größeren Teams: mehrere Teilteams durch Scrum Master koordiniert
- Arbeitsablauf im Team wird vom Team selbst geregelt
- Projektplanung: Eng mit dem Kunden werden Hauptaufgaben identifiziert („Product backlog“)
- Scrum Team schätzt Aufwände; wählt mit Kunden aus dem „Product backlog" wichtigste nächste Aufgaben für kommende Iteration (=Sprint, 30 Tage) aus
- Nach jedem Sprint wird mit dem Kunden analysiert, was erreicht wurde und wie das Projekt verbessert werden kann
- Kanban enthält sechs Kernpraktiken
