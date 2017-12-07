# Agile Workflows und Tools

**Autoren**:  
Jan T., Florian B. und Marc

## Continuous Integration (CI)

- Integration der Softwareentwicklung findet am Ende eines Projektes statt
  - Dauer der Integrationsphase liegt bei Wochen oder Monate, je nach Projektgröße und Komplexität
- "source repository"
  - zwei Entwickler können unabhängig voneinander Software für das selbe Produkt schreiben
  - regelmäßige Integration im Repo
  - einzelne Inkremente der Entwickler werden im Repo zusammengeführt
  - wird vom CI-Server integriert
- Voraussetzung
  - neben Produktiv-Code sind Tests zu entwickeln
- CI-Server
  - prüft durch die Tests, dass einzelnen Inkremente funktionsfähig bleiben
  - Ergebnis wird den jeweiligen Entwicklern zurück gegeben -> Fehler kann sofort behoben werden
  
![CI](vorlesung2/bilder/CI.png "Continuous Integration")

Durch CI ist der integrierte Code noch nicht bereit in Produktion zu gehen. Einzelne Komponenten funktionieren zwar miteinander, jedoch wurde das Produkt (die Software) noch nicht in einer "production-like environment" getestet und verifiziert.
- Vorteil von CI
  - Integration -> täglicher Geschäft
  - "Big-Bang" Integration einer Entwicklung wird vermieden
CI ist notwendig um Continuous Delivery durchzuführen.

-----------------------------------------------------------------------------------------------------------------

## Continuous Delivery

- Continuous Delivery
  - alle Beschriebenen CI Schritte
  - der integrierte Quelltext kann automatisiert auf verschiedenen Umgebungen getestet wird. 
 
- Umgebungen sehr ähnlich zu einer potentiellen Produktiv-Umgebung
- „Deployment pipeline" 
  - Deployen und Testen auf den verschiedenen Umgebungen
- Unterschiedlich viele Umgebungen
  - hängt ab von Projekt, Team oder Organisation 
  
![CD](vorlesung2/bilder/CD.png "Continuous Delivery")
  
Vor der Produkt-Umgebung werden die drei Umgebungen (Development, Test, Staging) durchlaufen.
In jeder Umgebung wird der Quelltext unterschiedlich getestet. 
Mit jeder erfolgreich durchlaufenen Umgebung wächst die Wahrscheinlichkeit, dass der Quelltext auch in der Produktiv-Umgebung lauffähig sein wird.

-----------------------------------------------------------------------------------------------------------------

## Continuous Deployment

Continuous Deployment geht noch einen Schritt weiter und automatisiert ebenfalls die Übergabe in die Produktion.
- Voraussetzung
-- erfolgreicher Durchlauf aller Schritte aus den Continuous Integration und Delivery
- Jeder einzelne Commit kann potentiell automatisiert in der Produktion ankommen
- Zusammengefasst
  - Commit erfolgreich integriert
  - alle Tests auf allen implementierten Umgebungen bestehen
Anschließend muss nicht mehr entschieden werden, ob der Mehrwert (Commit) in der Produktion verwendet werden kann, dies geschieht mit Continuous Deployment ebenfalls automatisiert.

![CD2](vorlesung2/bilder/CD2.png "Continuous Deployment")

-----------------------------------------------------------------------------------------------------------------

## Build Server

- Build Server als zentraler Ort, um den aktuellen Stand (Testergebnisse, kompilierten Artefakten) der Software einzusehen
- alle Prozesse laufen auf dem Server vollautomatisch
  - Fehler können durch falsche, ausgelassene oder vertauschte Prozess-Schritte ausgeschlossen werden
- isolierte Umgebung
  - garantiert gleiche Konfiguration bei den Entwickler-Rechnern (Tests laufen bei allen gleich ab)
- Build-Server erfolgreich und Entwickler-Rechner nicht
  - Fehlkonfiguration bei dem Entwickler
  - da der Build-Servers im Optimalfall möglichst nah an dem Produktivsystems liegt
  
Ein Build-Server kompiliert und testet nicht nur, sondern kann auch zur Durchführung von Continuous Delivery und Deployment verwendet werden.
Beispiele: Jenkins und Travis CI

 
