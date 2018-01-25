# Softwareprüfung
 
 ## Einordnung in den Entwicklungsprozess
 
 Autoren: Marc Schwettmann, Jan Tschech, Florian Buller

![Entwicklungsprozess](vorlesung15/bilder/entwP.png)

 ## Software Qualität
 
 ### Qualitätsmerkmale von Software 
 
 ![Qualitätsmerkmale](vorlesung15/bilder/qualiM.png)
 
 ### Gewichtung der Qualitätsmerkmale
 
 Die Qualitätsmerkmale werden unterschiedlich gewichtet und konkurrieren miteinander. Diese Tatsache kann im magischen Dreieck visualisiert werden.
 
 ![MagischesDreieck](vorlesung15/bilder/dreieck.png)

 ### Qualitätsmerkmale sind abhängig von der Perspektive der Aktoren
 
 - Benutzer
   - Zuverlässigkeit
   - Benutzerfreundlichkeit
   - Kompatibilität
   - Effizienz
 - Software-Hersteller
   - Wiederverwendbarkeit
   - Portabilität
 - Hersteller und Benutzer
   - Erweiterbarkeit
   - Anpassbarkeit
   
 ![benApliSof](vorlesung15/bilder/benApliSof.png)
 
 ### Qualitätsmerkmale sind abhängig von der Domäne und dem Projekt 
 
 Bei einem Betriebssystem ist das Zeitverhalten und die Stabilität wichtiger als bei einem Informationssystem, bei dem eher Funktionalität und Bedienbarkeit wichtig sind
 
 ## Qualitätsmaßnahmen
 
 ![Qualitätsmaßnahmen](vorlesung15/bilder/qualiMassnahmen.png)
 
 ### Aufgabe des Projektmanagements
 
 ![Projektmanagement](vorlesung15/bilder/projektManagement.png)
 
 ### Analytische QS-Verfahren
 
 ![Analytische QS-Verfahren](vorlesung15/bilder/aQSverfahren.png)
 
 ## Analysierende Verfahren
 
 ### Entwurfsziele
 
 - Niedrige Kopplung
   - Der Grad, zu dem die Klassen voneinander abhängig sind (Methodenaufrufe, Vererbung und Zugriff auf öffentliche Attribute)
   - Starke Kopplung entspricht starken Abhängigkeiten und erschwert Wiederverwendung und Wartbarkeit
 
 - Hohe Kohäsion
   - Misst, wie stark verwandt oder fokussiert die Aufgaben eines Elementes (z.B. Klasse, Komponente, Paket) sind
   - Niedrige Kohäsion lässt darauf schließen, dass in einer Klasse mehrere Funktionalitäten implementiert wurden und erschwert das Verständnis und die Wiederverwendbarkeit
 
 ### Quantitive und qualitative Aussagen über Softwarequalität
 
 - Qualitativ
   - mittels subjektiver Beurteilungsmethoden („gut“, „schlecht“) oder Review-Checklisten oder Codeinspektion
   
 - Quantitativ: Metrik 
 
 Eine Softwaremetrik ist eine Funktion, die eine Software-Einheit in einen Zahlenwert abbildet, der als der Erfüllungsgrad  einer Qualitätseigenschaft der Software-Einheit interpretiert wird. Eine Metrik ist ein interpretiertes Maß, das automatisch ermittelt werden kann und ein Indiz für die Qualität eines Produktes ist. Metriken sollen nur als Indikatoren betrachtet werden, d.h. gewonnene Aussagen müssen nachgeprüft werden. Dabei soll man Ergebnissen nicht blind vertrauen, sondern als Hilfsmittel  für eigene Urteilsfindung interpretieren. Es existieren zwei Arten von Metriken, Konventionelle Metriken und OO-Metriken.
 
 ![Metriken](vorlesung15/bilder/metriken.png)
 
 - Beispiel: SIZE (oder auch LOC=Lines of Code): Anzahl der Codezeilen
   - Umfang variiert mit der Sprache, Programmierstil, etc.
   - Leicht zu messen
   
 ### Zyklomatische Komplexität (McCabe)
 
 Zyklomatische Komplexität gibt Obergrenze für die Testfallanzahl für den Zweigüberdeckungstest an. Ein Codemaß, das die Komplexität von Kontrollflüssen in Methoden misst. Aber auch ein Quantitatives Maß für den erwarteten Testaufwand. Methoden mit einer hohen „Cyclomatic Complexity“ sind schwerer zu warten und zu testen. „Lange“ Methoden sind nicht unbedingt komplex. Folgt man McCabe, so sollen Methoden, für die z(G) > 10 gilt, einem Refactoring unterzogen werden.
 
 ![McCabe](vorlesung15/bilder/mcCabe.png)
 
 ### Zyklomatische Komplexität nach McCabe
  
 - Man konstruiere die Kontrollflussgraphen
 - Man messe die strukturelle Komplexität:
       Die zyklomatische Zahl z(G) eines Kontrollflussgraphen G ist:
		z(G) = e – n + 2 mit
		e = Anzahl der Kanten des Kontrollflussgraphen
		n = Anzahl der Knoten

 
 ![McCabe2](vorlesung15/bilder/mcCabe2.png)
 
 ### Beispiele für die zyklomatische Komplexität
 
 ![Zyklomatische Komplexität Bsp](vorlesung15/bilder/zykloKomplexBsp.png)
 
 ### Objektorientierte SW-Metriken
 
 In objektorientierten Programmen versagt die McCabe-Metrik, da die Kontrollflußkomplexit¨at der meisten Methoden gering ist (z (G) = 1). Metriken müssen deshalb das Zusammenspiel der Klassen betrachten – typischerweise anhand des (statischen) Objektmodells

 - Beispiel Werkzeuge für OO-Metriken
   - Checkstyle
   - JMetrik
   - Eclipse plugin
   
 ### Beispiele für OO SW-Metriken 
 
 - Lines of Code pro Methode: Maximum sollte unter 20 liegen
 - Methoden pro Klasse: sollte zwischen 3 und 15 liegen
 - Parameter pro Methode: sollte unter 6 liegen
 - Instanzvariablen pro Klasse: Die Zahl sollte unter 10 liegen
 - Depth of Inheritance Tree (DIT) = Anzahl der Oberklassen
 - Number Of Children (NOC) = Anzahl der direkten Unterklassen
 - Weighted Method per Class (WMC) = Anzahl der definierten Methoden
 - Coupling Between Object Classes (CBO) = Anzahl der benutzten Klassen
 - Lack of Cohesion in Methods (LCOM)
   - Aussage über die “Güte” der Kapselung. Kann Hinweis auf Entwurfsfehler sein
   - Es gibt unterschiedliche Varianten zur Berechnung von LCOM
 
 ### LCOM (Lack of Cohesion in Methods)
 
 LCOM (C) = Methodenpaare ohne gemeinsame Instanzvariablen minus Methodenpaare mit gemeinsamen Instanzvariablen (falls LCOM (C) < 0 => LCOM (C) = 0).
 Ziel: LCOM (C) = 0

 ![LCON](vorlesung15/bilder/LCON.png)

 ### Lack of Cohesion in Methods (LCOM*) = LCOM-HS (Henderson-Sellers) = LCOM5
 
 - LCOM* =  (avgNutzt – m)  /  (1 - m)
   - nutzt(a) die Zahl der Methoden, die eine Instanzvariable a der untersuchten Klasse nutzen 
   - avgNutzt der Durchschnitt aller Werte für alle Instanzvariablen
   - m die Anzahl aller Methoden der untersuchten Klasse
 - Ist der Wert nahe Null, handelt es sich um eine eng zusammenhängende Klasse
 - Ist der Wert nahe 1, ist die Klasse schwach zusammenhängend und man sollte über eine Aufspaltung nachdenken. Hinweis auf Entwurfsfehler
 - Hinweise
   - Es muss vorher festgelegt werden, ob Klassenvariablen und Klassenmethoden berücksichtigt werden sollen
   - Ist LCOM* benutzbar, wenn man auch get()- und set()-Methoden nutzt? 
 
 ### LCOM*-Beispiel
 
 ![LCON Bsp](vorlesung15/bilder/LCONbsp.png) 
 
 ## Testende Verfahren - Statische Tests
 
 - Analyse und Prüfung der Systembeschreibungen (z. B. Anforderungen, Entwurfsdiagramme, Quellcode, ...)
 - Ausführung des Systems nicht erforderlich
 
 ### Arten von testenden statischen Verfahren
 
 - Review
   - Überprüfung schriftlicher Dokumente durch Gutachter sowie Überprüfung von Code, Fortschritt, Qualität mit dem Ziel der Feststellung von Mängeln, Fehler, Inkonsistenzen, Unvollständigkeiten, Verstößen gegen Vorgaben, Richtlinien, Standards, Plänen
 - Walkthrough
   - abgeschwächte Form des Reviews
 - Audit
   - während ein Review das Ergebnis prüft, prüft ein Audit die Vorgehensweise und den Ablauf, also Prüfung des Wegs zum Ergebnis
 - Code-Inspektion
   - Diskussion des Source-Codes mit erfahrenen Softwareentwicklern. Dient zum Aufdecken von Fehlern und nicht zum Beheben von Fehlern dient
 - Statische Analyse
   - Werkzeuggestütztes Auffinden von Fehlern ohne direkte Ausführung des Systems mit dem Ziel, fehlerverdächtige Stellen des Systems zu lokalisieren
 - Formale Verifikation (Korrektheitsbeweis)
   - Verifikation ist die Beurteilung eines Systems, um festzustellen, ob die Resultate einer gegebenen Entwicklungsphase den Vorgaben aus einer vorhergehenden entsprechen
 
 ## Testende Verfahren - Dynamische Tests

- Das Systemverhalten wird überwacht und gegenüber dem spezifiziertem Verhalten geprüft
- Das System wird mit Testdaten ausgeführt und sein Verhalten beobachtet
- Validierung ist die Beurteilung, ob ein Softwaresystem die spezifizierten Anforderungen erfüllt

### Was ist Testen?

- Testen dient dazu, ein Programm mit der Absicht auszuführen, Fehler zu finden
- Die Korrektheit eines Programms kann durch Testen nicht bewiesen werden
- Tests dienen zum Nachweis der korrekten Umsetzung der Anforderungen und der Aufdeckung von Fehlern

### Was ist Debugging?

- Debugging dient der Lokalisierung der Ursache der Fehler

### Grundsätze der Softwareprüfung

- Systematisch prüfen: Prüfung zuerst planen und anschließend nach Vorschriften durchführen
- Softwareprüfung kann nur gegen Vorgaben (Anforderungen oder Vergleichsresultate) erfolgen
- Die Prüfung muss reproduzierbare Ergebnisse liefern
- Ergebnisse werden mit Testprotokollen dokumentiert
- Die Planung der Softwareprüfung wird früh im Entwicklungsprozess begonnen
- Häufig mehr Zeilen Testcode als "normaler" Code
- Ein Softwareentwickler sollte die von ihm implementierte Funktionalität nicht selber testen (außer Unittests). Dies sollte eine unabhängige Testperson übernehmen
- Fehlerkorrektur sollte sorgfältig durchgeführt werden:
	- Wahrscheinlichkeit für richtige Korrektur beim ersten Versuch oft gering
	- Vermeidung der Einschleusung neuer Fehler
	- Wiederholung der zugehörigen Testfälle (Regressionstest)

## Testarten

![Testarten](vorlesung15/bilder/Testarten.png)

### Unittests

- Ziel: Aufdeckung aller Abweichungen der Implementierung von der Spezifikation
- Einzelfunktionen werden isoliert von den anderen Klassen des Systems geprüft

### Integrationstest

- Ziel: Aufdeckung von Fehlern in Schnittstellen und im Zusammenspiel zwischen integrierten Klassen
- Das Zusammenwirken der Komponenten und Klassen wird geprüft

### Systemtest

- Aufdeckung aller Abweichungen des Systemverhaltens in Bezug auf das in der Anforderungsdefinition spezifizierte Systemverhalten
- Überprüft wird:
	- die vollständige Erfüllung der Benutzeranforderungen
	- die Korrektheit der Ergebnisse
	- die Robustheit gegen fehlerhafte Eingabedaten
	- die nicht funktionalen Anforderungen

![Testarten2](vorlesung15/bilder/Testarten2.png)

### Abnahmetest

- Akzeptanztest (End-To-End-Test)
- Test wird mit realen Daten und unter realen Einsatzbedingungen durchgeführt
- Aufdecken aller Fehler, die auf Missverständnisse bei Absprachen zwischen Benutzer und Entwickler beruhen
- Test gegen Abnahmekriterien, die in der Anforderungsdefinition festgelegt wurden

![Ebenen_Tests](vorlesung15/bilder/Ebenen_Tests.png)

## Weitere Testarten

### Regressionstest

- "Fertige" Software wird geändert durch neue Anforderungen oder Bugfixes
- Gibt es nach den Änderungen Auswirkungen auf die alten Testergebnisse?

![Regressionstest](vorlesung15/bilder/Regressionstest.png)

### Stresstest

- Verhalten beim Überschreiten definierter Grenzen wird getestet

### Test des Speicherverhaltens (C/C++)

- Gibt es Speicherlöcher (Memory leaks)?
- Wird auf bereits freigegebenen Speicherplatz erneut zugegriffen?
- Wird Speicherplatz mehrfach freigegeben und gibt es Zugriff auf ein Array jenseits der Grenzen?

### GUI-Test

- Capture & Replay: Alle Mausbewegungen und Tastatureingaben werden aufgezeichnet und können dann als Test erneut abgespielt werden

### Penetrationstest

- Simulierter Hackerangriff

### Lasttest

- Testet das System auf Zuverlässigkeit und das Einhalten der Spezifikation innerhalb des erlaubten Grenzbereichs
- Test auf Performance: Transaktionsrate bzw. Antwortzeiten 
- Test auf Skalierbarkeit: Anzahl der Endbenutzer und das Datenvolumen
- Gibt es Zugriffskonflikte konkurrierender Benutzer?

### Performancetest

- Wie oft wird jede Methode aufgerufen?
- Welche Methide ruft wie oft welche andere Methode auf?
- Wie viel Prozent der Gesamtlaufzeit wird mit der Ausführung einer bestimmten Methode verbracht?
- Operationen, die am meisten Laufzeit in Anspruch nehmen, werden optimiert

## Ermittlung von Testfällen

![Ableitung_von_Testfällen](vorlesung15/bilder/Ableitung_von_Testfaellen.png)

Vollständiges Testen ist in der Regel unmöglich, daher wird nur stichprobenartig getestet. Das Ziel dabei ist es mit möglichst wenig Testfällen möglichst viele Fehler zu finden.

### Verfahren zur Testfallermittlung

#### Funktionsorientierter Test (Black-Box-Test)

- Testfallauswahl aufgrund der Modulspezifikation
- Interne Struktur kann unbekannt sein
- Prüft definierte Schnittstellen auf Funktionalität
- Ausgehend von der Spezifikation des zu untersuchenden Objekts werden verschiedene Eingaben definiert, deren gewünschtes Resultat aus der Spezifikation abzuleiten ist
- Ziel: Umfassende Prüfung der spezifizierten Funktionalität

#### Strukturorientierter Test (White-Box-Test)

- Testfallauswahl aufgrund der internen Struktur
- Codereview: Prüft die Details der Logik
- Klassenspezifikation muss ebenfalls bekannt sein
- Es wird die Struktur des zu untersuchenden Programms analysiert und versucht, möglichst alle Ablauf alternativen (if, while) durchzuspielen
- Ziel: Für jeden möglichen Pfad durch das Testobjekt soll das Verhalten des Testobjekts in Abhängigkeit von den Eingabedaten festgestellt werden

Verfahren zur Testfallermittlung:

![Verfahren_zur_Testfallermittlung](vorlesung15/bilder/Verfahren_zur_Testfallermittlung.png)

#### Black-Box-Test: Error Guessing

- Kein systematisches Verfahren
- Auswahl der Testfälle aufgrund von Erfahrung
- Ergänzt die Methoden zur Testfallbestimmung
- Typische Fehler:
	- Sonderfälle werden nicht berücksichtigt
	- Grenzwerte werden nicht behandelt
	- Endlosschleifen
	- Fehlende Initialisierung von Variablen
	- Falsche logische Operationen

#### Black-Box-Test: Äquivalenzklassenbildung

- Gleichartige Eingabedaten werden zu Klassen zusammengefasst
- Es werden gültige Äquivalenzklassen (Normalfall) und ungültige Äquivalenzklassen (Sonderfall) gebildet
- Die Bildung der Äquivalenzklassen zerlegt die Menge der Eingaben in disjunkte Teilmengen

##### Regeln zur Bildung von Äquivalenzklassen

- Mögliche Eingaben müssen bekannt sein
- Für einfache Zahlenparameter: Intervall mit gültigen Werden
- Wenn explizit eine Menge von Werten vorgegeben ist: Jeder Wert stellt eine Äquivalenzklasse dar

##### Beispiel für Äquivalenzklassen

Spezifikation:
- Einem Konstruktor zur Verwaltung von Studierenden wird ein Name, ein Geburtsjahr und ein Fachbereich übergeben.
- Einschränkungen:
	- Das Namensfeld darf nicht leer sein
	- Das Geburtsjahr muss zwischen 1900 und 2000 liegen
	- Es könne nur die Fachbereiche aus einer Aufzählung (FBING, FBBWL und FBPOL) übergeben werden

![Äquivalenzklasse](vorlesung15/bilder/Aequivalenzklassen.png)

##### Testfallerzeugung aus Äquivalenzklassen

- Gültige Äquivalenzklassen:
	- möglichst viele Klassen in einem Test kombinieren
- Ungültige Äquivalenzklassen:
	- Auswahl eines Wertes aus einer ungültigen Äquivalenzklasse in Kombination mit Werten, die ausschließlich aus gültigen Äquivalenzklassen entnommen sind
	- Für alle ungültigen Eingabewerte muss eine Fehlerbehandlung existieren

![Testfallerzeugung_aus_Äquivalenzklassen](vorlesung15/bilder/Testfallerzeugung_aus_Aequivalenzklassen.png)

#### Black-Box-Test: Grenzwertanalyse

- Untersuchung von Äquivalenzklassen wird um die Untersuchung der Grenzen ergänzt
- Auswahl von Testfällen für solche Grenzfälle

Testfälle nach einer Äquivalenzklassenanalyse und Grenzwertanalyse:

![Grenzwertanalyse](vorlesung15/bilder/Grenzwertanalyse.png)

#### Strukturorientierter Test (White-Box-Test) 

- Betrachtung des Ein-/Ausgabeverhaltens und der inneren Struktur des Testobjekts -> Test der implementierten Realisierung

- Ziel: Für jeden möglichen Pfad durch das Testobjekt soll das Verhalten des Testobjekts in Abhängigkeit von den Eingabedaten festgestellt werden

- Auswahl der Testfälle aufgrund der Kenntnis der Ablaufstrukturen des Testobjekts

- Wahl der Testfälle:
	- Jede Klasse und jede Methode des Testobjekts wird mindestens einmal aufgerufen
	- Jeder Zweig wird mindestens einmal durchlaufen Möglichst alle Pfade werden durchlaufen

##### Der Kontrollflussgraph (KFG) 

- Ist ein gerichteter Graph

KFG(P) =def   G = (V, E, VStart, VZiel)

- V: Menge der Knoten (Anweisungen des Programms)
- E: Teilmenge von V×V: Menge der Kanten (Nachfolgerelation bezüglich der Ausführung des Programms)
- VStart , VZiel  aus V: Ausgewählte Knoten für Start, Ende des Programms (VZiel kann auch eine Menge von Knoten sein)

![KFG](vorlesung15/bilder/kfg.png)

- Methode gibt Quadrat aller positiven geraden Zahlen, sonst 0 zurück

##### Normalisierung eines KFG

Wunsch: Graph sollte unabhängig von der Formatierung sein

Folgende Regeln, mit denen mehrere Knoten k1,k2,...,kn, die nacheinander durchlaufen werden können, also k1,k2,...,kn, zu einem Knoten verschmolzen werden.
- Die Knotenfolge wird bei jedem Durchlauf immer nur über k1 betreten, es gibt außer den genannten Kanten keine weiteren Kanten, die in k2,...,kn enden.
- Die Knotenfolge wird bei jedem Durchlauf immer nur über kn verlassen, es gibt außer den genannten Kanten keine weiteren Kanten, die in k1,...,kn-1 beginnen.
- Die Knotenfolge ist maximal bezüglich a) und b).

##### White box Tests

- C0: Anweisungsüberdeckung (Statement Coverage): Jede Anweisung des Programms wird mindestens einmal durchlaufen.
- C1: Zweigüberdeckung (Branch Coverage): Jeder Zweig der Anwendung wird mindestens einmal durchlaufen. Z.B. einmal if und einmal else oder einmal while und einmal nicht while.
- C2: Pfadüberdeckung (Path Coverage): Jeder mögliche Pfad der Anwendung wird mindestens einmal durchlaufen.
- C3: Bedingungsüberdeckung (Condition Coverage): Jede Bedingung und jede Teilbedingung wird mindestens einmal durchlaufen und ist einmal true und einmal false.

##### Anweisungsüberdeckung (C0)

Ziel: alle Anweisungen des Programms durch Wahl geeigneter Testdaten mindestens einmal ausführen, alle Knoten des KFG mindestens einmal besuchen.

![Anweisungsüberdeckung (C0)](vorlesung15/bilder/C0.png)

![Anweisungsüberdeckung (C0)](vorlesung15/bilder/C02.png)

##### Anweisungsüberdeckung (C1)

Ziel: alle Kanten des KFG überdecken, d.h. alle Zweige des Programms einmal durchlaufen

![Anweisungsüberdeckung (C1)](vorlesung15/bilder/C1.png)

![Anweisungsüberdeckung (C1)](vorlesung15/bilder/C12.png)

##### Zusammenfassung C0 & C1

Vorteile der Anweisungsüberdeckung: 
- einfach
- geringe Anzahl von Eingabedaten
- nicht ausführbare Programmteile werden erkannt

Nachteil der Anweisungsüberdeckung:
- Logische Aspekte werden nicht überprüft

Deshalb: 
- Zweigüberdeckungstest gilt als das Minimalkriterium im dynamischen Softwaretest
- Schließt den Anweisungsüberdeckungstest ein
- Fordert die Ausführung aller Zweige eines KFG
- Jede Entscheidung mindestens einmal wahr und falsch 

Nachteile der Zweigüberdeckung: 
- Fehlende Zweige werden nicht automatisch entdeckt 
- Kombinationen von Zweigen sind unzureichend geprüft 
- Komplexe Bedingungen werden nicht analysiert 
- Schleifen werden nicht ausreichend analysiert 


##### Testansätze zusammengefasst

![Testansätze zusammengefasst](vorlesung15/bilder/C12.png)


#### Unittests

- Die Anzahl der Code-Zeilen für Unittests übersteigt bei weitem die Anzahl der Zeilen des zu testenden Codes.
- Ein Unittest testet genau eine Klasse.
- A test is not a unit test if:
	- It talks to the database
	- It communicates across the network
	- It touches the file system
	- It can’t run at the same time as any of your other unit tests
	- You have to do special things to your environment (such as editing config files) to run it.

##### Test - Fixture

- Ein Testfall sieht in der Regel so aus, dass eine bestimmte Konfiguration von Objekten aufgebaut wird, gegen die der Test läuft.
- Diese Menge von Testobjekten wird auch als Test-Fixture bezeichnet.
- Damit fehlerhafte Testfälle nicht andere Testfälle beeinflussen können, wird die Test-Fixture für jeden Testfall neu initialisiert.
- In der Methode setUp werden Variable initialisiert und Mit der Methode tearDown werden wertvolle Testressourcen (z.B. Datenbank- oder Netzwerkverbindungen) wieder freigegeben.


##### TestSuite

- Um eine Menge von Tests zusammen ausführen zu können, werden die Tests zu TestSuites zusammengefasst.
- Mit JUnit können beliebig viele Tests in einer TestSuite zusammengefasst  werden.
- pro Package eine TestSuite-Klasse definieren.

#### TDD

![TDD](vorlesung15/bilder/tdd.png)


#### Zusammenspiel von Klassen testen

Software Engineering - Softwareprüfung


Zu sa m m e n sp ie l v on  Kla sse n  t e st e n

- Bis jetzt wurde nur eine Klasse betrachtet, die keine Assoziation zu anderen zu testenden Klassen hat
- Weil die Implementierung von anderen Klassen noch nicht vorhanden sind, muss man die Implementierung „simulieren“, so dass man die eigene Klasse testen kann -> Test-Double
- Liegt die Klasse vor, die man temporär durch den Test-Double prüfen wollte, können diese Tests mit der realen Klasse wiederholt werden
- Test-Doubles dienen auch für die Implementierung von Klassen, die auf Ressourcen (z.B. Datenbanken) zugreifen, die nicht immer verfügbar sind
- Test-Doubles wurden früher per Hand programmiert. Heutzutage kann man diese per Software automatisch erzeugen lassen:
- Beispiele: jMock, EasyMock, Mockito
- Achtung:
	- Test-Doubles sind oft aufwändig in der Erstellung und müssen bei Änderungen am Code mit verändert werden und geben keine Garantie dafür, dass die Software keine Fehler enthält.


#### Test Doubles

![Test Doubles](vorlesung15/bilder/testdoubles.png)

- Mock: Dynamische und konfigurierbare Laufzeit-Implementierung eines Interfaces oder Klasse, für die Rückgabewerte von Methoden definiert werden.
- Stub: Fragmentartige Implementierung als Stellvertreter, genutzt zum Testen. 
- Dummy: Ersatzklasse ohne Implementierung, um das Testen zu ermöglichen. Wird herumgereicht, aber nicht benutzt. (z.B. um eine Parameterliste einer Methode zu füllen). Muss existieren, aber eine „Interaktion“ mit einem Dummy ist nicht angedacht.
- Dummies und Stubs werden erzeugt, um die Testumgebung „lauffähig“ zu machen und werden nicht für die eigentliche „Verifikation“ benutzt. Ein Dummy wird als „Wert“ herumgereicht, während ein Stub Daten an die zu testende Klasse zurückgibt („indirekte Inputs“).
- Spy: Ein Mock, der die Aufrufe von Methoden etc. zählt
- Spies und Mocks werden benutzt, um die Korrektheit des Kommunikationsablauf zwischen zu testender Klasse und den daran beteiligten Klassen zu überprüfen („indirekte Outputs“).
- Fake: Funktionierende, einfach aufzusetzende, simplifizierte Implementierung mit "gehackter Funktionalität", also nicht verwendbar in Produktion (zum Beispiel eine In-memory-Datenbank). Fakes werden in Integrationstests verwendet.
- Fakes spielen dieselbe Rolle wie Dummies oder Stubs. Sie werden erzeugt, um die Testumgebung lauffähig zu machen, aber werden nicht für die Verifikation benutzt. 
- Test doubles werden nicht für direkte Outputs der SUT benutzt.











