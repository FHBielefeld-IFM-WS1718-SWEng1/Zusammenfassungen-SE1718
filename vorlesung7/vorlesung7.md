# Systemanalyse mit UML-Aktivitätsdiagrammen

## Pragmatisches Schritt für Schritt Vorgehensmodell

![Pragmatisches Schritt für Schritt Vorgehensmodell](vorlesung7/bilder/schrittfuerschritt.png)

### Kanten (Kontrollfluss / Objektfluss)

Unterschieden wird zwischen dem Objekt- und Kontrollfluss. Bei der verkürzten Schreibweise wird der Objektknoten direkt an die Aktion angeheftet. Die Ausgabe einer Aktion ist die Eingabe der nächsten Aktion.

![Bildschirmfoto 2017-11-29 um 18.02.48](img/Bildschirmfoto 2017-11-29 um 18.02.48.png)



**Verkürzte Schreibweise**

![Bildschirmfoto 2017-11-29 um 18.02.59](img/Bildschirmfoto 2017-11-29 um 18.02.59.png)

![Bildschirmfoto 2017-11-29 um 18.03.15](img/Bildschirmfoto 2017-11-29 um 18.03.15.png)

Die Steuerung der Abläufe in einem Aktivitätsdiagramm erfolgt durch Token (Marken) in Form von Kontrolltoken und Datentoken. Ein Token definiert hierbei den aktuellen Zustand der Verarbeitung. Tokens werden erzeugt, wandern und verarbeitet 

![Bildschirmfoto 2017-11-29 um 18.04.24](img/Bildschirmfoto 2017-11-29 um 18.04.24.png)

Bei der Erzeugung eingangsloser Knoten (Startknoten, Signalempfangsknoten) wird ein Token erzeugt. Bei der Aufspaltung bzw. Synchronisation gibt es einen Token pro ausgehendem Fluss.

Bei der Wanderung entlang einer Kante wird eine Aktion gestartet, der Token trifft ein und wandert weiter. Ist die Aktion beendet, wählt der Token einen ausgehenden Fluss.

Bei Aufspaltung/Synchronisation bzw. bei einem Endknoten werden alle eingehende Token verarbeitet

![Bildschirmfoto 2017-11-29 um 18.05.42](img/Bildschirmfoto 2017-11-29 um 18.05.42.png)

![Bildschirmfoto 2017-11-29 um 18.05.46](img/Bildschirmfoto 2017-11-29 um 18.05.46.png)

![Bildschirmfoto 2017-11-29 um 17.38.56](img/Bildschirmfoto 2017-11-29 um 17.38.56.png)

Die Anordnung erfollt in gekennzeichnenten Bereichen, damit wird beschrieben, wer oder was für eine Menge von Knoten verantwortlich ist oder welche gemeinsame Eigenschaft sie kennzeichnet. Eine horizontale und vertikale Darstellung sowie Matrix oder hierarchisch ist erlaubt.

![Bildschirmfoto 2017-11-29 um 17.41.45](img/Bildschirmfoto 2017-11-29 um 17.41.45.png)

![Bildschirmfoto 2017-11-29 um 17.41.50](img/Bildschirmfoto 2017-11-29 um 17.41.50.png)

![Bildschirmfoto 2017-11-29 um 17.41.56](img/Bildschirmfoto 2017-11-29 um 17.41.56.png)

![Bildschirmfoto 2017-11-29 um 17.42.53](img/Bildschirmfoto 2017-11-29 um 17.42.53.png)

![Bildschirmfoto 2017-11-29 um 17.43.11](img/Bildschirmfoto 2017-11-29 um 17.43.11.png)

### Signale und Ergeignisse

**Signal senden**

Aktion, die ein Signal sendet unabhängig vom Zeitpunkt des Auftretens

![Bildschirmfoto 2017-11-29 um 17.45.44](img/Bildschirmfoto 2017-11-29 um 17.45.44.png)

![Bildschirmfoto 2017-11-29 um 17.45.48](img/Bildschirmfoto 2017-11-29 um 17.45.48.png)

**Signa empfangen**´

Aktion, die auf ein Signal wartet unabhängig vom Zeitpunkt des Auftretens. Wenn keine einlaufender Fluss: kann beliebig oft Signale empfangen

![Bildschirmfoto 2017-11-29 um 17.46.39](img/Bildschirmfoto 2017-11-29 um 17.46.39.png)

![Bildschirmfoto 2017-11-29 um 17.46.43](img/Bildschirmfoto 2017-11-29 um 17.46.43.png)

**Zeitereignis empfangen**

Aktion, die ein Signal sendet unabhängig vom Zeitpunkt des Auftretens

![Bildschirmfoto 2017-11-29 um 17.46.57](img/Bildschirmfoto 2017-11-29 um 17.46.57.png)

![Bildschirmfoto 2017-11-29 um 17.47.13](img/Bildschirmfoto 2017-11-29 um 17.47.30.png)

![Bildschirmfoto 2017-11-29 um 17.47.45](img/Bildschirmfoto 2017-11-29 um 17.47.57.png)

###  Unterbrechungsbereich

![Bildschirmfoto 2017-11-29 um 17.51.11](img/Bildschirmfoto 2017-11-29 um 17.51.11.png)

**Motivation:** Dadurch können Exceptions modelliert oder das Verhalten von Fehlerzuständen visualisiert werden.



#### Exception Handler

Die Anordnung der Aktionen in gekennzeichnete Bereiche. Der Exception Handler beschreibt, wer oder was für eine Menge von Knoten verantwortlich ist oder welche gemeinsame Eigenschaft sie kennzeichnet. Dabei sind horizontale und vertikale Darstellung sowie Matrix oder hierarchisch ist erlaubt.

![Bildschirmfoto 2017-11-29 um 17.52.29](img/Bildschirmfoto 2017-11-29 um 17.52.29.png)

![Bildschirmfoto 2017-11-29 um 17.52.44](img/Bildschirmfoto 2017-11-29 um 17.52.44.png)



### Aktivitätsdiagramme Beispiele

#### Aktivitätsdiagramme mit Objektfluss

![Bildschirmfoto 2017-11-29 um 17.53.31](img/Bildschirmfoto 2017-11-29 um 17.53.31.png)

![Bildschirmfoto 2017-11-29 um 17.54.04](img/Bildschirmfoto 2017-11-29 um 17.54.04.png)

![Bildschirmfoto 2017-11-29 um 17.54.14](img/Bildschirmfoto 2017-11-29 um 17.54.14.png)

### Best practices

Ideal ist es, wenn der Startknoten links oben und der Endknoten rechts unten ist. Ausserdem sollte der Name der Aktion sinnvoll gewählt werden. Keine Aktionen, die keine Ausgabepfeile besitzen (black holes) sowieso solche, die keine Eingabepfeile besitzen (miracles).

Ausserdem sollten die Bedingungen eindeutig identifiziert und die Menge der Bedingungen vollständig sowie eindeutig sein.



**Falsch**

![Bildschirmfoto 2017-11-29 um 17.55.58](img/Bildschirmfoto 2017-11-29 um 17.55.58.png)

**Richtig**

![Bildschirmfoto 2017-11-29 um 17.56.01](img/Bildschirmfoto 2017-11-29 um 17.56.01.png)

**Falsch**

![Bildschirmfoto 2017-11-29 um 17.56.23](img/Bildschirmfoto 2017-11-29 um 17.56.23.png)

**Richtig**

![Bildschirmfoto 2017-11-29 um 17.56.26](img/Bildschirmfoto 2017-11-29 um 17.56.26.png)

#### **Synchronisieren** von parrallelen Kanten

![Bildschirmfoto 2017-11-29 um 17.57.25](img/Bildschirmfoto 2017-11-29 um 17.57.25.png)

#### Alternative Abläufe zusammenführen

![Bildschirmfoto 2017-11-29 um 17.57.50](img/Bildschirmfoto 2017-11-29 um 17.57.50.png)

![Bildschirmfoto 2017-11-29 um 17.57.54](img/Bildschirmfoto 2017-11-29 um 17.57.54.png)

### Zusammenfassung

![Bildschirmfoto 2017-11-29 um 17.58.17](img/Bildschirmfoto 2017-11-29 um 17.58.17.png)

![Bildschirmfoto 2017-11-29 um 17.58.21](img/Bildschirmfoto 2017-11-29 um 17.58.21.png)