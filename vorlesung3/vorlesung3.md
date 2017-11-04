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

##### XP Paarprogrammierung
- alle Programmiertätigkeiten werden im Paar ausgeführt
	- Rollenverteilung Fahrer und Beifahrer
		- Fahrer denkt an Implementierung der Programm-Logik
		- Beifahrer denkt strategisch, führt ständige Durchsicht durch
- führt zu höhrer Qualität

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

#####Product-Owner (Auftraggeber)
Dieser legt die Anforderungen sowie den Auslieferungstermin fest. Zudem pflegt er das Product-Backlog und das Budget zur Verfügung und akzeptiert beziehungsweise lehnt Arbeitsergebnisse ab. Weiterhin priorisiert er die Anforderungen und passt diese an.

#####Scrum-Master
Der Scrum-Master stellt die Einhaltung der Scrum-Werte und -Techniken sicher. Er sorgt dafür, dass das Entwicklungsteam funktional und produktiv ist und schützt das Entwicklungsteam vor äußeren Störungen. Zudem versucht er das Team anzustoßen, bei der Vorbereitung zu helfen und diverse Hindernisse zu beseitigen. Dazu unterstützt der Scrum-Master die Zusammenarbeit zwischen allen Rollen.

#####Scrum-Team (Entwicklungsteam)
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






