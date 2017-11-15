# Agile Workflows und Tools

## Continuous Integration (CI)

- Integration der Softwareentwicklung findet am Ende eines Projektes statt
  - Dauer der Integrationsphase liegt bei Wochen oder Monate, je nach Projektgröße und Komplexität
- "source repository"
  - zwei Entwickler können unabhängig voneinander Software für das selbe Produkt schreiben
  - regelmäßige Integration im Repro
  - einzelne Inkremente der Entwickler werden Repro zusammengeführt
  - wird vom CI-Server integriert
- Voraussetzung
  - neben Produktiv-Code sind Tests zu entwickeln
- CI-Server
  - prüft durch die Tests, dass einzelnen Inkremente funktionsfähig bleiben
  - Ergebnis wird den jeweiligen Entwicklern zurück gegeben -> Fehler kann sofort behoben werden
