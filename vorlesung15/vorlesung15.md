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
	- die vollständige Erfükkung der Benutzeranforderungen
	- die Korrektheit der Ergebnisse
	- die Robustheit gegen fehlerhafte Eingabedaten
	- die nichtfunktionalen Anforderungen

![Testarten2](vorlesung15/bilder/Testarten2.png)

### Abnahmetest

- Akzeptanztest (End-To-End-Test)
- Test wird mit realen Daten und unter realen Einsazubedingungen durchgeführt
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

- Capture & Replay: Alle Mausgewegungen und Tastatureingaben werden aufgezeichnet und können dann als Test erneut abgespielt werden

### Penetrationstest

- Simulierter Hackerangriff

### Lasttest

- Testet das System auf Zuverlässigkeit und das Einhalten der Spezifikation innerhalb des erlaibten Grenzbereichs
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

Vollständges Testen ist in der Regel unmöglich, daher wird nur stichprobenartig getestet. Das Ziel dabei ist es mit möglichst wenig Testfällen möglichst viele Fehler zu finden.

### Verfahren zur Testfallermittlung

#### Funktionsorientierter Test (Black-Box-Test)

- Testfallauswahl aufgrund der Modulspezifikation
- Interne Struktur kann unbekannt sein
- Prüft definierte Schnittstellen auf Funktionalität
- Ausgehend von der Spezifikation des zu untersuchenden Objekts werden verschiedene Eingaben definiert, deren gewünschtes Resultat aus der Spetifikation abzuleiten ist
- Ziel: Umfassende Prüfung der spezifizierten Funktionalität

#### Strukturorientierter Test (White-Box-Test)

- Testfallauswahl aufgrund der internen Struktur
- Codereview: Prüft die Details der Logik
- Klassenspezifikation muss ebenfalls bekannt sein
- Es wird die Struktur des zu untersuchenden Programms analysiert und versucht, möglichst alle Ablaufalternative (if, while) durchzuspielen
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
- Wenn explizit eine Menge von Werten vorgegenen ist: Jeder Wert stellt eine Äquivalenzklasse dar

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
	- Auswahl eines Wertes aus einer ungültigen Äquivalenzklasse in Kobination mit Werten, die ausschließlich aus gültigen Äquivalenzklassen entnommen sind
	- Für alle ungültigen Eingabewerte muss eine Fehlerbehandlung existieren

![Testfallerzeugung_aus_Äquivalenzklassen](vorlesung15/bilder/Testfallerzeugung_aus_Aequivalenzklassen.png)

#### Black-Box-Test: Grenzwertanalyse

- Untersuchung von Äquivalenzklassen wird um die Untersuchung der Grenzen ergänzt
- Auswahl von Testfällen für solche Grenzfälle

Testfälle nach einer Äquivalenzklassenanalyse und Grenzwertanalyse:

![Grenzwertanalyse](vorlesung15/bilder/Grenzwertanalyse.png)