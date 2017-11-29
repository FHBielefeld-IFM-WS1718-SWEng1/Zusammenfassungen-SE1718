## Systemanalyse mit UML-Aktivitätsdiagrammen

### Pragmatisches Schritt für Schritt Vorgehensmodell

![Pragmatisches Schritt für Schritt Vorgehensmodell](vorlesung7/bilder/schrittfuerschritt.png)

### Lernziele

- Wissen, was man unter der Aktivität „Systemanalyse" versteht
- UML-Aktivitätsdiagramme modellieren können

###  Grundlagen

#### Einordnung in den Entwicklungsprozess

![img1](Vorlesung7/Bilder/img1.PNG)



![img2](Vorlesung7/Bilder/img2.PNG)

#### Die Anforderungsanalyse

Die Anforderungsanalyse beschreibt Anwendungsfälle und Akteur, spezifiziert Geschäftsvorfälle mit Text und definiert die GUI.

#### Die Systemanalyse

Dient dem detailierten Verständnis des Softwaresystems bevor das System realisiert wird, um Probleme im Vorfeld zu entdecken. Präzisiert was Auftraggeber und Anwender wirklich wollen, dabei wird zwischen Anforderung und Implementierung klar getrennt. (Systemanalyse vs. Softwareentwurf)

Dies schafft ein einheitliches Verständnis zwischen Kunden und Entwicklern sowie innerhalb des Entwicklungsteams. Ermöglicht Priorisierung der Anforderungen und Entscheidung über ihre Realisierung.

#### Bsp für eine Systemanalysemodell

- Die Systemarchitektur wird visuell auf abstraktem Niveau zum Beispiel als Client-Server-Architektur oder als Peer-to-Peer Architektur in Form eines „Box-and-arrows“-Diagramms.

  ​

  ![img3](Vorlesung7/Bilder/img3.PNG)

  ​

- Einordnung der Systemanalyse in Analogie zu einem Hausbau

  ​

![img4](Vorlesung7/Bilder/img4.PNG)



#### UML-Modelle in der Objektorientierten Systemanalyse

1. Anforderungsdefinition (insbesondere Use Cases)
2. Analyseklassendiagramm (Domain Object Model)
   1. Vollständige Darstellung der fachlichen Daten-Anforderungen an das System
   2. Ausgangsmodell für die Entwicklung des OOD-Klassendiagramms
3. Ausgangspunkt der Aktivitätsdiagramme sind Use Case-Diagramme und textuelle Use Case–Beschreibungen
   1. Textuelle Use Cases Definitionen werden mittels Aktivitätsdiagrammen visualisiert, diese dienen auch der Spezifikation von Testfällen und damit zur Systemvalidierung
4. Mögliche Einsatzgebiete von Aktivitätsdiagrammen sind 
   1. Die Beschreibung Use Case-übergreifender Abläufe	
   2. Die Spezifikation des Ablaufs innerhalb eines Use Cases
   3. Die Dokumentation des Kontrollflusses einer Operation

### Aktivitätsdiagramme

#### Aufgaben, Zwecke und Einsatzgebiete

Aktivitätsdiagramme dienen der modellierung von Abläufen in Datenflüssen eines Systems, Generierung von Testfällen und der Geschäftsprozessmodellierung. Die Darstellung übergreifender Abläufe über Use Cases hinweg (Geschäftsvorfall) kann visualisiert werden. Damit können sowohl sequentielle als auch parallele Abläufe modelliert werden. Die Darstellung von zeitlich-logischen Abläufen in Form von aufeinanderfolgenden Aktivitäten inklusive Verzweigungen und parallelen Vorgängen werden kenntlich gemacht. 

Die Diagramme stellen quasi den Algorithmus einer Operation dar.

![img5](Vorlesung7/Bilder/img5.PNG)



#### Von Use Case zum Aktivitätsdiagramm

Zu jedem Use Case genau ein Aktivitätsdiagramm modellieren

- Erzeugen Sie aus den Use Case-Schritten Aktionen.
- Zerlegen Sie die Aktionen ggfs. mit einem Aktivitätsdiagramm, so dass sie stets genau einen fachlichen Arbeitsschritt repräsentieren.
- Ergänzen Sie den Ablauf um alle bekannten fachlichen Ausnahmen und fachlichen Ablaufvarianten, so dass das Diagramm eine vollständige Beschreibung aller zulässigen Ablaufmöglichkeiten darstellt

Modellierung des Objektflusses

- Beschreiben Sie zu jeder Aktion die zu verarbeitenden und die resultierenden Geschäftsobjekte.
- Beschreiben Sie, bei welchen ausgehenden Transitionen bzw. Bedingungen welche Objekte bzw. Objektzustände resultieren.

### Notationselemente für Aktivitätsdiagramme

#### Grundlegende Elemente

![img6](Vorlesung7/Bilder/img6.PNG)



![img14](Vorlesung7/Bilder/img14.PNG)



- Eine Aktion ist zentrales Element innerhalb eines Aktivitätsdiagramms

- Modelliert einen einzelnen Schritt einer Aktivität

- Über Kanten mit anderen Elementen verbunden

  ​

![img10](Vorlesung7/Bilder/img10.PNG)



![img8](Vorlesung7/Bilder/img8.PNG)



![img7](Vorlesung7/Bilder/img7.PNG)



![img9](Vorlesung7/Bilder/img9.PNG)



- Startknoten (Initialknoten)
  - Startpunkt eines Ablaufs in einem Aktivitätsdiagramm
  - Pro Diagramm muss mindestens ein Startknoten oder ein Start über Objektknoten existieren
  - Mehrere Startknoten sind erlaubt
- Endknoten (Aktivitätsendknoten)
  - Beendet den beschriebenen Ablauf (d.h. alle Aktionen und Kontrollflüsse)
  - Pro Diagramm muss wenigstens ein Endknoten oder ein Ende über ein Objektknoten existieren
- Ablaufende
  - Beendet einen einzelnen Kontrollfluss
  - Konsumiert ein einzelnes Token

![img11](Vorlesung7/Bilder/img11.PNG)



- Entscheidungsknoten / Entscheidung (Decision)
  - Verzweigung des Kontrollflusses
  - Hat ein oder mehrere ausgehende Kanten versehen mit Bedingungen (Guards)
  - Hat genau einen Eingang
- Vereinigungsknoten (Merge) Syncronisationsknoten (Merge)
  - Führt mehrere eingehende Kanten zu einer ausgehenden Kante zusammen
  - Decision u. Merge treten immer paarweise auf
  - Alle Pfade aus einer Decision müssen im selben Merge-Knoten zusammenkommen
- Paralleisierungsknoten / Teilung (Fork)
  - Der eingehende Kontrollfluss wird auf mehrere ausgehende, nebenläufige Kontrollflüsse aufgeteilt
  - Ohne Bedingung
  - Erlaubt die parallele Ausführung mehrere Kontrollflüsse
- Synchronisationsknoten / Synchronisation (Join)
  - Wartet auf alle eingehende Kontrollflüsse bevor mit dem ausgehenden Kontrollfluss fortgefahren wird
  - Synchronisiert parallele Kontrollflüsse



![img13](Vorlesung7/Bilder/img13.PNG)



Beispiel 

![img15](Vorlesung7/Bilder/img15.PNG)



- Durch die Aktion „Auftrag erfassen wird ein Objekt vom Typ „Auftrag“ als Ergebnis geliefert.
- Dieser gelieferte Auftrag wird in der Folgeaktion „Aufträge drucken“ als Eingabeparameter benutzt

#### Softwareentwicklungsprozess

![img12](Vorlesung7/Bilder/img12.PNG)


### Kanten (Kontrollfluss / Objektfluss)

Unterschieden wird zwischen dem Objekt- und Kontrollfluss. Bei der verkürzten Schreibweise wird der Objektknoten direkt an die Aktion angeheftet. Die Ausgabe einer Aktion ist die Eingabe der nächsten Aktion.

![Bildschirmfoto_2017-11-29_um_18.02.48](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.02.48.png)



**Verkürzte Schreibweise**

![Bildschirmfoto_2017-11-29_um_18.02.59](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.02.59.png)

![Bildschirmfoto_2017-11-29_um_18.03.15](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.03.15.png)

Die Steuerung der Abläufe in einem Aktivitätsdiagramm erfolgt durch Token (Marken) in Form von Kontrolltoken und Datentoken. Ein Token definiert hierbei den aktuellen Zustand der Verarbeitung. Tokens werden erzeugt, wandern und verarbeitet 

![Bildschirmfoto_2017-11-29_um_18.04.24](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.04.24.png)

Bei der Erzeugung eingangsloser Knoten (Startknoten, Signalempfangsknoten) wird ein Token erzeugt. Bei der Aufspaltung bzw. Synchronisation gibt es einen Token pro ausgehendem Fluss.

Bei der Wanderung entlang einer Kante wird eine Aktion gestartet, der Token trifft ein und wandert weiter. Ist die Aktion beendet, wählt der Token einen ausgehenden Fluss.

Bei Aufspaltung/Synchronisation bzw. bei einem Endknoten werden alle eingehende Token verarbeitet

![Bildschirmfoto_2017-11-29_um_18.05.42](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.05.42.png)

![Bildschirmfoto_2017-11-29_um_18.05.46](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_18.05.46.png)

![Bildschirmfoto_2017-11-29_um_17.38.56](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.38.56.png)

Die Anordnung erfollt in gekennzeichnenten Bereichen, damit wird beschrieben, wer oder was für eine Menge von Knoten verantwortlich ist oder welche gemeinsame Eigenschaft sie kennzeichnet. Eine horizontale und vertikale Darstellung sowie Matrix oder hierarchisch ist erlaubt.

![Bildschirmfoto_2017-11-29_um_17.41.45](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.41.45.png)

![Bildschirmfoto_2017-11-29_um_17.41.50](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.41.50.png)

![Bildschirmfoto_2017-11-29_um_17.41.56](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.41.56.png)

![Bildschirmfoto_2017-11-29_um_17.42.53](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.42.53.png)

![Bildschirmfoto_2017-11-29_um_17.43.11](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.43.11.png)

### Signale und Ergeignisse

**Signal senden**

Aktion, die ein Signal sendet unabhängig vom Zeitpunkt des Auftretens

![Bildschirmfoto_2017-11-29_um_17.45.44](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.45.44.png)

![Bildschirmfoto_2017-11-29_um_17.45.48](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.45.48.png)

**Signa empfangen**´

Aktion, die auf ein Signal wartet unabhängig vom Zeitpunkt des Auftretens. Wenn keine einlaufender Fluss: kann beliebig oft Signale empfangen

![Bildschirmfoto_2017-11-29_um_17.46.39](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.46.39.png)

![Bildschirmfoto_2017-11-29_um_17.46.43](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.46.43.png)

**Zeitereignis empfangen**

Aktion, die ein Signal sendet unabhängig vom Zeitpunkt des Auftretens

![Bildschirmfoto_2017-11-29_um_17.46.57](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.46.57.png)

![Bildschirmfoto_2017-11-29_um_17.47.13](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.47.30.png)

![Bildschirmfoto_2017-11-29_um_17.47.45](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.47.57.png)

###  Unterbrechungsbereich

![Bildschirmfoto_2017-11-29_um_17.51.11](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.51.11.png)

**Motivation:** Dadurch können Exceptions modelliert oder das Verhalten von Fehlerzuständen visualisiert werden.



#### Exception Handler

Die Anordnung der Aktionen in gekennzeichnete Bereiche. Der Exception Handler beschreibt, wer oder was für eine Menge von Knoten verantwortlich ist oder welche gemeinsame Eigenschaft sie kennzeichnet. Dabei sind horizontale und vertikale Darstellung sowie Matrix oder hierarchisch ist erlaubt.

![Bildschirmfoto_2017-11-29_um_17.52.29](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.52.29.png)

![Bildschirmfoto_2017-11-29_um_17.52.44](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.52.44.png)



### Aktivitätsdiagramme Beispiele

#### Aktivitätsdiagramme mit Objektfluss

![Bildschirmfoto_2017-11-29_um_17.53.31](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.53.31.png)

![Bildschirmfoto_2017-11-29_um_17.54.04](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.54.04.png)

![Bildschirmfoto_2017-11-29_um_17.54.14](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.54.14.png)

### Best practices

Ideal ist es, wenn der Startknoten links oben und der Endknoten rechts unten ist. Ausserdem sollte der Name der Aktion sinnvoll gewählt werden. Keine Aktionen, die keine Ausgabepfeile besitzen (black holes) sowieso solche, die keine Eingabepfeile besitzen (miracles).

Ausserdem sollten die Bedingungen eindeutig identifiziert und die Menge der Bedingungen vollständig sowie eindeutig sein.



**Falsch**

![Bildschirmfoto_2017-11-29_um_17.55.58](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.55.58.png)

**Richtig**

![Bildschirmfoto_2017-11-29_um_17.56.01](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.56.01.png)

**Falsch**

![Bildschirmfoto_2017-11-29_um_17.56.23](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.56.23.png)

**Richtig**

![Bildschirmfoto_2017-11-29_um_17.56.26](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.56.26.png)

#### **synchronisieren** von parrallelen Kanten

![Bildschirmfoto_2017-11-29_um_17.57.25](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.57.25.png)

#### Alternative Abläufe zusammenführen

![Bildschirmfoto_2017-11-29_um_17.57.50](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.57.50.png)

![Bildschirmfoto_2017-11-29_um_17.57.54](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.57.54.png)

### Zusammenfassung

![Bildschirmfoto_2017-11-29_um_17.58.17](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.58.17.png)

![Bildschirmfoto_2017-11-29_um_17.58.21](vorlesung7/bilder/Bildschirmfoto_2017-11-29_um_17.58.21.png)