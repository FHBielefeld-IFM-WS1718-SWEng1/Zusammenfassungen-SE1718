# Software Engineering
## Einleitung
"Software Engineering" = "Softwaretechnik"
### Was ist Software?
Software ist ein umfassenderer Begriff als „Programm“
* Software besteht ebenfalls aus der zugehörigen Dokumentation
* Software enthält alle Elemente, die für den Betrieb notwendig sind. z.B. Datenbankskripte, Dokumentation, Betriebshandbücher, usw.

*„Programme, zugehörige Daten und Dokumentationen, die es zusammengefasst erlauben, mit Hilfe eines Computers Aufgaben zu erledigen.“*</br>
![Eisberg](/BilderVorlesung1/Eisberg.png?raw=true "Eisberg der Software")
#### Softwaresystem
* Ein Softwaresystem ist ein System, dessen Bestandteile)und Elemente aus Software bestehen („innere“ Sicht des Softwareentwicklers)

#### Softwareprodukt
* Ein Softwareprodukt ist ein für einen 
Auftraggeber erstelltes Softwaresystem
(„äußere“ Sicht)</br>
![SWSystem](/BilderVorlesung1/SWSystem.png?raw=true "Software System")
#### Softwarearten
* Systemsoftware(z.B. Betriebssystem)
* Anwendungssoftware (z.B. Büroanwendungen, Office)
* Standardsoftware (anpassbare Software für anonyme Kunden, z.B. SAP)
* Individualsoftware
    * Speziell für einen Kunden/Auftraggeber entwickelte Software
    * Exakt auf die Bedürfnisse des Kunden zugeschneidertes Produkt
    * Relativ zeitaufwändige und teure Entwicklung
    * Typische Beispiele: Software zur Unterstützung spezieller Geschäftsprozesse
* Eingebettete Systeme (Steuerungssoftware für Geräte)
* Echzeitsysteme (z.B. Flugüberwachung und Kraftwerkssteuerung)
* Informationssysteme (datenbankgestützte Verwaltung von Information), oft webbasiert

#### Eigenschaften von Software
* Software kann man nicht anfassen: Software ist immateriell
* Entwicklungsfortschritt ist nicht objektiv messbar
* Anders als materielle Produkte verschleißt Software nicht
* Software verschleißt zwar nicht, altert aber dennoch
    * Die Umgebung, in der Software eingesetzt wird, ändert sich ständig
    * Software muss daher diesen Änderungen immer wieder angepasst werden

### Klassischer Software Lebenszyklus</br>
![Wasserfallmodell](/BilderVorlesung1/Wasserfallmodell.PNG?raw=true "Wasserfallmodell")
#### Phasen eines Vorgehensmodells
* Anforderungsermittlung: Wie findet man heraus, welche Eigenschaften (insbesondere Funktionalität) die zu konstruierende Software haben soll?
* Analyse: Wie beschreibt man dann diese Eigenschaften?
* Entwurf: Wie strukturiert man die Software so, dass sie sich leicht bauen und flexibel verändern lässt?
* Implementierung: Wie realisiert man effizient und fehlerfrei die Software?
* Wartung: Wie verändert man Software, die keine solche Struktur hat oder deren Struktur man nicht (mehr) versteht?
* Test: Wie vermeidet man Mängel in Software oder deckt sie auf?
* Übergeordnet
    * Prozessmanagement: Wie organisiert man die Arbeit einer Softwareabteilung, um regelmäßig kostengünstige und hochwertige Resultate termingerecht zu erzielen?

**Die Lehrveranstaltung orientiert sich an diesen Phasen eines Softwareprojekts als „roter Faden“ und stellt die Phasen anhand von Vorgehensmodellen vor, wobei verschiedene UML-Diagramme verwendet werden.**

### Rollen in der Softwareentwicklung
#### Begriffe der Rollen
* Eine Rolle beschreibt eine Menge von zusammengehörigen Aufgaben und Befugnissen (oft auch notwendige Qualiﬁkationen)
* Eine Rolle wird von Personen wahrgenommen
* Eine Person kann mehrere Rollen einnehmen
* Eine Rolle kann von mehreren Personen eingenommen werden
* Nicht in jeder Softwareentwicklung treten alle Rollen auf, abhängig von Art und Größe des Projekts

#### Ziel der Rolle
* Kooperation zwischen den beteiligten Personen durch Verständnis für die Aufgaben

#### Beteiligte
* Auftraggeber
    * Geben Geld, haben unterschiedliche Bedürfnisse
* Benutzer
    * Setzen Software ein
    * Manchmal mit Auftraggeber identisch
* Manager
    * Fällen während der Entwicklung die organosatorischen Entscheidungen
* Berater
    * Unterstützen den Kunden in der Definition der Anforderungen
* Entwickler
    * Definieren und bauen Software
    * in verschiedenen Rollen (d.h. mit verschiedenartigen Aufgaben)

</br>

![RolleBeiAuftragsarbeit](/BilderVorlesung1/RolleBeiAuftragsarbeit.PNG?raw=true "Rollen bei Auftragsarbeit") 

</br>

![RollenInDerSoftwareentwicklung](/BilderVorlesung1/RollenInDerSoftwareentwicklung.PNG?raw=true "Rollen in der Softwareentwicklung")


### Rollen aus der Informatik-Persperpektive

##### **Projekmanager**
* Ziel: erfolgreiche Projektdurchführung
* Phasen: für alle Phasen des Projekts zuständig
* Aktivitäten:
    * Planung des Projekts: 
        * Projektorganisation
        * Kostenschätzung und Planung 
        * Erstellung eines Projektplans
    * Kontrolle des Projekts: 
        * Produktverfolgung,
        * Planüberprüfung
        * Produktivitätsüberwachung
    * Steuerung des Projekts: 
        * Projektkoordination

##### **Anforderungsanalytiker**
* Aufgabe: kümmert sich um die Aufnahme und Überprüfung von Anforderungen an das System
* Phasen: vor allem in den "frühen" Phasen der Prduktentwicklung vorhanden
* Aktivitäten:
    * Ermitteln und Erkennen von Benutzer-Anforderungen: 
        * Ist-Analyse: „Was macht das derzeitige System?“ 
        * Soll- Analyse: „Was soll das zukünftige System tun?“
    * Machbarkeitsstudie: 
        * Bewertung der Ist- und Soll-Analyseergebnisse
        * Integration unterschiedlicher Sichten/Ziele: Kommunikation mit Anwendern, Kunden etc. und Übereinstimmung der Beteiligten bzgl. der deﬁnierten Anforderungen
        * Erstellung eines Anforderungsdokuments

##### **Software-Architekt**
* Aufgabe: Architektur des Systems
    * kümmert sich somit um den Übergang vom Problem zur Realisierung 
* Aktivitäten:
    * Zuordnung von Anforderungen auf Komponente/Subsysteme 
    * Grobentwurf: 
        * Subsysteme 
        * evtl. grobgranulare Komponenten und deren Beziehungen 
    * Sicherstellung von Qualitätsattributen (Struktur des Systems beeinﬂusst Qualitätsattribute)
    * Dokumentation der Systemarchitektur

##### **Software-Designer**
* Aufgabe: fertigt eine Beschreibung des Verhaltens, der Daten und der Funktionen des Systems  an. Er entwirft eine „implementierungsnahe“ Speziﬁkation der Anforderungen an das Softwaresystem („technische Anforderungen“)
* Aktivitäten:
    * Modellierung/ Beschreibung der Anforderungen aus „Implementierungssicht“  (Kommunikation mit Architekt und Programmierer)
    * Feinentwurf: Detaillierter Entwurf des Systems (Komponenten, Interfaces, Klassen)

##### **Programmierer/Entwickler**
* Aufgabe: kümmert sich um die programmiertechnische Umsetzung (Realisierung, Implementierung) des Entwurfs
* Aktivitäten:
    * Programmierung der einzelnen Komponenten
    * Dokumentation des Programmcodes
    * Deﬁnition der speziﬁschen Algorithmen
    * Beachtung von Standards
    * Entwickler-Test der Module (z.B. JUnit-Tests) 
    * Code-Reviews

##### **Tester**
* Aufgabe: führt das System aus, um Hinweise auf Fehler zu ﬁnden (Systemtests, Integrationstests). 
* Aktivitäten: 
    * Detaillierung von Testplan, Testentwurf und Testfällen
    * Durchführung von Tests (Dokumentation der Testbedingungen und Testergebnissen)
    * Überprüfung der Zusammenarbeit der Komponenten
    * Überprüfung des Gesamtsystems

    <br /> 
    _Abwesenheit von Fehlern kann durch Testen **NICHT** garantiert werden._
    
##### **Konﬁgurationsmanager**
* Aufgabe: kümmert sich um die Festlegung der Regelungen für Konﬁgurations- und Produktverwaltung. 
* Aktivitäten:
    * Überwachung der Konﬁguration des Produkts Konﬁgurationskontrolle und Statusverfolgung
    * Nachvollziehbarkeit und Konsistenz: Sicherstellung von Sichtbarkeit, Verfolgbarkeit und Kontrollierbarkeit eines Produkts und seiner Teile im Lebenszyklus
##### **Administrator**
* Aufgabe: kümmert sich um den Betrieb des Softwaresystems
* Aktivitäten:
    * Installation der Software
    * Überwachung der laufenden Software durch Monitoring von Log-Files
    * Einspielen von Software-Updates

### Was ist ein Softwareprojekt?
* Ein Projekt ist ein Vorhaben, das im wesentlichen durch die Einmaligkeit der Bedingungen in ihrer Gesamtheit gekennzeichnet ist, wie z.B. 
    * Zielvorgabe 
    * Zeitliche, finanzielle, personelle oder andere Begrenzungen

#### Unterschiedliche Projektgrößen
Die Herstellung großer Softwaresysteme mit Millionen von Codezeilen unterscheidet sich auch qualitativ und nicht nur quantitativ von der Herstellung kleiner Software.
<br />
<br />
Unterschiede:
* Die  Komplexität  großer  Softwaresysteme  übersteigt  die  von  einem Entwickler zu einem Zeitpunkt zu beherrschende Komplexität
* Die Wahrscheinlichkeit für die Korrektheit eines Systems von vielen „Modulen“ ist wesentlich kleiner als die Wahrscheinlichkeit für die Korrektheit einzelner „Module“
* Langlebigkeit und Versionierung großer Softwaresysteme ist problematisch
* Kommunikation unter vielen beteiligten Personen gestaltet sich schwierig

|Projektgröße|Kriterien|Rollen|Warum?|Beispiele|
|--|--|--|--|--|
|Light|Bis zu 6 Personen </br>Monate (PM) : 0-8</br> Anzahl Technologien: <5|Kunde, Mangager, Programmierer, Teseter|Besteht meistens aus nur einer Person, die alle Rollen erfüllt|Rechenprobleme und Algorithmen|
|Medium|10-30 Personen</br> 9-24 PM</br>Technologien 5-12|Kunde, Projektleiter, Analytiker, Programmierer, Tester, Controller|Projekt umfangreicher Zusammenarbeit mehrerer Personen notwendig|Buchhaltung und Lagerverwaltung|
|Heavy|50-100 Personen</br>25-15PM </br> 12-20 Technologien|Kunde, Management, wirtschaftlicher und technischer Projektleiter, Gruppenleiter, Analytiker, Controller, Programmierer, Tester, Qualitätssicherer| Das Projekt ist für Einzelne nicht mehr überschaubar. Es wird Aufgeteilt in Gruppen mit Struktur des Ganzen.|Compiler und Datenbank|
|Super Heavy|Ab 100 Personen</br> > 45PM</br>> 20 Technologien|siehe Heavy| Raumfahrt, Atomkraftwerk</br>elektronische Börse|siehe Heavy|

### Software Qualität
#### Qualitätsmerkmale für Software
#### Perspektive auf Softwarequalität
#### Intressenskonflikte
* Funktionalität vs. Benutzbarkeit
	* Je überladener, um so schwerer zu erlernen
* Funktionalität vs. schnelle Entwicklung
    * Viel Funktionalität zu implementieren braucht Zeit
* Kosten vs. Robustheit
	* Sparen an Qualitätssicherung
* Kosten vs. Wiederverwendbarkeit
	* Quick and dirty
* Effizienz vs. Portabilität
	* Effizienz durch Speziallösung für bestimmtes Betriebssystem, DBMS, ...
* Abwärtskompatibilität vs. Lesbarkeit
	* Viele Sonderfälle für Altversionen erschweren die Lesbarkeit

### Probleme in der Software Entwicklung

*Bild Standish Group Chaos Report*

- 18% aller SW-Projekte wurden ohne verwertbares Ergebnis abgebrochen
- 53% aller SW-Projekte hatten nach Beendigung eine Budget- und/oder Terminüberschreitung von über 60%
- 29% aller SW-Projekte in "time, quality & money" abgewickelt worden
 
*Baum Bild*

#### Ursachen für schlechte Software-Qualität
- Zu wenig Ressourcen bzw. falsche Schätzung benötigter Ressourcen
- Unrealistische Zeit- und Kostenpläne
- Schlechtes Projektmanagement
- Häufige Änderung der Anforderungen
- Qualitätsmängel bei extern vergebenen Aufgaben
- Pflege von Altsystemen ist schwierig
- Fehlende Planung (unklare Verantwortlichkeit)
- Projekt wird nicht mehr benötigt
- Vielzahl an anderen Dokumenten neben dem Source-Code
- Unrealistische oder unausgesprochene Projektziele
- Unvollständige/Schlecht definierte Anforderungen (unklare Zielvorstellung)
- Die Komplexität und Lebensdauer von Software nimmt zu
- Nicht gemanagte Risiken
- Schlechte Kommunikation zwischen Kunden, Entwicklern und Benutzern
- Anwender nicht involviert
- Verwendung unausgereifter Technologien
- Unfähigkeit, die Projektkomplexität in den Griff zu kriegen
- Nachlässige Entwicklungspraktiken
- "Politische" Gründe der Beteiligten
- Kommerzieller Druck
- Unvollständige Dokumentation

**-> Ursachen in Organisation, Technologie, Methodik**

#### Schlüsselfaktoren für Projekterfolg
*Bild Schlüsselfaktoren für Projekterfolg*

### Softwarekosten

- Die Wartung der Software ist teurer als die Entwicklung
- Kosten für das Testen sind fast so hoch wie die Entwicklungskosten
- Kosten variieren je nach Typ des zu entwickelnden Systems, sowie nach den Anforderungen an die Systemattribute, wie Performance und Systemzuverlässigkeit
- Verteilung der Kosten ist abhängig vom verwendeten Vorgehensmodell
- Die Mehrzahl der Softwareentwickler sind mit Pflegearbeiten beschäftigt

#### Fehlerentstehung und Fehlererkennung in verschiedenen Projektstadien
*Bild Fehler in der Softwareentwicklung in %*

#### Verteilung der Fehlerkosten
*Bild Verteilung der Fehlerkosten*

**-> Je später ein Fehler entdeckt wird, desto teurer ist die Beseitigung**

### Was ist Software Engineering
Folgende Bedingungen sind gegeben:
- mehr als eine Person entwickelt die Software
- mehr als eine Version der Software existiert

Software-Engineering soll helfen, diese Probleme nicht entstehen zu lassen oder zu beseitigen.

#### Aufbau Informatik
*Bild Aufbau Informatik*

#### Aufbau Software Engineering
*Bild Aufbau Software Engineering*

*Bild Software + Engineering*

Software Engineering ist der Einsatz von Methoden, Werkzeugen und Vorgehensmodellen zum Erstellen und Betreiben von Software mit dem Ziel, die Softwarekosten bei der Entwicklung, Wartung und Erweiterung von Programmsystemen zu senken und gleichzeitig eine hohe Qualität zu erreichen.

#### Ziele des Software Engineerings
- Schnelle und effiziente Entwicklung des Produkts (Entwicklungsaspekt)
- Einhaltung der geforderten Qualitätsmerkmale (Qualitätssicherungsaspekt)
- Kontrollierte Projektabwicklung (Managementaspekt)
- Sicherstellung der Wartbarkeit, Erweiterbarkeit und Wiederverwendbarkeit (Wartungsaspekt)
 
#### Software Engineering
- Stellt die Qualität in den Mittelpunkt (Kundezufriedenheit, Sicherheit)
- Basiert auf (agilen) Vorgehensmodellen
- Entwicklung wird methodisch durchgeführt (OOA/OOD mit UML)
- Softwarewerkzeuge zur Beherrschung der Komplexität
 
### Zusammenfassung
- Software Engineering ist eine Ingenieur-Disziplin, die sich mit allen Aspekten der Softwareentwicklung und Softwarewartung beschäftigt
- Ziel des Software Engineerings ist die Erreichung einer hohen Softwarequalität und die Minimierung der Softwarekosten
- Software Engineering ist mehr als Technik und befasst sich mit Konzepten, Methoden und Werkzeugen für die professionelle Softwarenentwicklung
- Softwareprodukte bestehen aus Programmen und der Dokumentation
- Software Ingenieure arbeiten in Teams in Software Projekten methodisch und strukturiert und kommunizieren mit Kunden und Teammitgliedern
- Software Ingenieure beherrschen die Technik und lassen sich nicht von der Technik beherrschen
- Der Softwareentwicklungsprozess besteht aus Phasen, die bei der Entwicklung des Softwareprodukts involviert sind. Die grundlegenden Phasen sind Analyse, Entwurf, Implementierung, Integration, Test, Wartung und Weiterentwicklung