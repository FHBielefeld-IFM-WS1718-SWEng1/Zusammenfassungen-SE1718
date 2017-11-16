# OOA/OOD mit UML-Diagrammen

## Lernziele
- Objektorientierte Modellierung kennenlernen
- Objektorientierte Analyse (OOA) & Objektorientiertes Design (OOD) kennenlernen
- Überblick über relevante UML-Diagrammtypen und deren Zusammenspiel
- Wissen, welche UML-Diagramme in welchen Phasen der Softwareentwicklung eingesetzt werden

## Modellbildung
![Modellbildung](vorlesung5/bilder/Bild1.png "Modellbildung")

## OOA / OOD mit UML

### Analysemethoden
- Richtlinien zur Vorgehensweise in der Analysephase
- Beispiele:
        - Strukturierte Analyse (SA)     
        - Objektorientierte Analyse (OOA)

### OOA / OOD
OOA und OOD zerlegen das Softwaresystem mit objektorientierten Verfahren in handhabbare Teile, dadurch ergeben sich Vorteile wie:

- Durchgängige und konsistente Beschreibung über alle Phasen der Softwareentwicklung hinweg 
(Bei Nutzung von Objektorientierten Sprachen -> Gleiche Konzepte für Analyse, Design und Implementierung)
- Erhöhte Verständlichkeit durch Objekte als Konzept aus der realen Welt
- Erhöhte Wiederverwendbarkeit durch relativ abgeschlossene Objektdefinitionen und -implementierungen

### Objektorientierte Analyse (OOA)
Die OOA ist die fachliche Beschreibung der Systemanforderungen und die Präzisierung des Problems.
Es beschreibt was das System tun soll und nicht wie es implementiert werden soll.
Außerdem soll für die Verringerung der Komplexität herausgefiltert werden, welche die wichtigsten Aspekte für die Aufgabe sind.

- Untersuchung und Beschreibung des Systembereichs unabhängig von der Programmiersprache
- Testen von Einheiten bereits vor ihrer Fertigstellung
- Ableitung eines Prototypen

### Objektorientiertes Design (OOD)
Das OOD ist eine Erweiterung des OOA-Modells zur Abbildung des Realitätsmodells auf den Lösungsbereich. Es soll als Vorstufe der Umsetzung direkt in einer Programmiersprache implementierbar sein.

- Erweiterung um systemnahe Klassen
        - Schnittstellen
        - Benutzungsoberfläche
        - Datenhaltung
        - Verteilung
- Hinzufügen von Klassen, Attributen und Methoden, die für die Realisierung gebraucht werden (z.B. Datenhaltung in Form einer verketteten Liste)
- Einbeziehung bestehender Entwürfe und Klassenbibliotheken (z.B.UI-Library) in das Design

## UML
UML ist eine einheitliche Sprache zur Beschreibung von Softwaresystemen und ist insbesondere für die Analyse und den Entwurf in der frühen Phase der Softwareentwicklung geeignet.
Es enthält verschiedene Diagrammtypen, die sich gegenseitig ergänzen und verschiedene Systemaspekte hervorheben. 

- Ermöglicht die Kommunikation zwischen Entwickler-Entwickler und Entwickler-Benutzer
- Bildet den Problembereich möglichst genau auf ein (Programmier-) Modell ab
- Analogie zu einem Bauplan für ein Haus (Grundriss, Außenansichten, Werkpläne etc.)
- Besitzt einige Freiheitsgrade bei der Modellierung

### UML Diagrammtypen
![UML Diagrammtypen Übersicht](vorlesung5/bilder/Bild2.png "Diagrammtypen Übersicht")

![UML Diagrammtypen 1](vorlesung5/bilder/Bild3.png "UML Diagrammtypen 1")
![UML Diagrammtypen 2](vorlesung5/bilder/Bild4.png "UML Diagrammtypen 2")
![UML Diagrammtypen 3](vorlesung5/bilder/Bild5.png "UML Diagrammtypen 3")

## Modelle und UML-Diagramme
UML wird zur Darstellung und Modellierung eines Software-Systems benutzt. Ein (Software-)System lässt sich durch eine Menge von Funktionen, Anwendungsfällen und Diensten modellieren. Auch eine prozessorientierte Darstellung durch eine Menge von Prozessen, Abläufen, Vorgängen und Workflows ist möglich. Ein System kann aber auch nur aus Daten und Objekten bestehen. Die Bezieheungen untereinander und die Struktur stehen dann im Fokus.
- Ein System kann und soll in Subsysteme zerlegt werden. Dies besteht aus unabhängigen Komponenten.
- Es wird zwischen statischen und dynamischen Modellen unterschieden.
- Die "UML-Pyramide" veranschaulicht die Zugehörigkeiten grafisch und ist nicht direkt umzusetzen, sondern soll grob den gesamten Prozess aufzeigen.
![UML-Pyramide](vorlesung5/bilder/Bild6.png "UML-Pyramide")

Die Diagramme verfeinern sich von oben nach unten auf der Pyramide. Das statische Modell zeigt eine Gesamtsicht auf das Problemfeld und lässt unwesentliche Details weg, während das dynamische Modell das Systemverhalten darstellt und zeitlicher Ablauf, Zustände und Übergänge im Vordergrund stehen.

Ein Use-Case (Anwendungsfall) beschreibt Anforderungen und bestimmt den Funktionsumfang.
- Außensicht auf das Produkt
- Kommunikationsgrundlage mit Kunden
- Testgrundlage/ Erstellung früher Prototypen

Ein dynamisches Aktivitätsdiagramm beschreibt genau einen Workflow, wodurch sich bereits erste Klassen, Objekte und Beziehungen untereinander gewinnen lassen.
Ein statisches Paketdiagramm besteht aus zusammenhängenden Klassen und ist ohne weitere Kenntnis der einzelnen Klassen verstehbar.
Paket- und Klassendiagramme geben einen Überblick über die Ergebnisse des statischen Softwareentwurfs.
Sequenz- und Kommunikationsdiagramme werden benutzt wenn das Verhalten im Vordergrund steht. Sie beschreiben den Nachrichtenaustausch in einem System.
In Zustandsübergangsdiagrammen geht es um den Zustand eines einzigen Objekts im Verlauf. Es dient zum Aufspüren neuer Attribute und Methoden.

## Zuordnung der UML-Diagrammtypen zu Phasen der Softwareentwicklung
- Anforderungen -> Use-Case Diagramm
- Geschäftsprozesse -> Aktivitätsdiagramm
- Statische Softwarestruktur -> Klassendiagramm
- Dynamisches Verhalten der Software -> Sequenzdiagramm, Zustandsdiagramm
- Struktur von Softwarekomponenten/ Bibliotheken -> Komponentendiagramm
- Zuordnung von Software auf Rechnersysteme -> Verteilungsdiagramm

### Zusammenspiel von UML Diagrammtypen
![Zusammenspiel von UML Diagrammtypen](vorlesung5/bilder/Bild7.png "Zusammenspiel von UML Diagrammtypen")
- Der Ablauf (Workflow) eines Use-Cases wird durch ein Aktivitätsdiagramm modelliert.
- Szenarien eines Use-Cases werden durch Interaktionsdiagramme (z.B. Sequenzdiagramme) modelliert.
- Ein Use-Case wird durch Klassendiagramme strukturiert und die Klassen werden in Interaktionsdiagrammen verwendet.
- Das Verhalten einer Klasse wird in einem Zustandsdiagramm modelliert.
- Ein Paketdiagramm strukturiert Klassen zu größeren Einheiten.

## Pragmatisches "Schritt für Schritt" Vorgehensmodell
![Vorgehensmodell 1](vorlesung5/bilder/Bild8.png "Schritt für Schritt Vorgehensmodell 1")
![Vorgehensmodell 2](vorlesung5/bilder/Bild9.png "Schritt für Schritt Vorgehensmodell 2")
![Vorgehensmodell 3](vorlesung5/bilder/Bild10.png "Schritt für Schritt Vorgehensmodell 3")
![Vorgehensmodell 4](vorlesung5/bilder/Bild11.png "Schritt für Schritt Vorgehensmodell 4")
![Vorgehensmodell 5](vorlesung5/bilder/Bild12.png "Schritt für Schritt Vorgehensmodell 5")
