# Systemanalyse mit UML-Aktivitätsdiagrammen

## Pragmatisches Schritt für Schritt Vorgehensmodell

![Pragmatisches Schritt für Schritt Vorgehensmodell](vorlesung7/bilder/schrittfuerschritt.png)

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