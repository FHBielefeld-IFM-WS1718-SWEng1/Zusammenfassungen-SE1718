Informationen für Contributer
=============================

Dieses Repo verwendet [Github Pages](https://pages.github.com/) zusammen mit [docute](https://github.com/egoist/docute) für die Darstellung.

Vorausetzung dafür ist das alle Daten auf dem branch "gh-pages" vorhanden ist.
<br><br>

Die empfohlene Ordnerstruktur ist `vorlesungX/vorlesungX.md` und `vorlesungX/bilder/*` wobei X die Nummer der Vorlesung ist.
<br>
Bitte darauf achten, dass Bilderlinks in docute keinen relativen Pfad verwenden können, statt `/bilder/bild.png` muss `vorlesungX/bilder/bild.png` verwendet werden. Dies wird zwar in Github nicht vernünftig angezeigt, funktioniert aber in docute.

Um die docute Darstellung lokal zu testen, muss dieses zuerst [installiert](https://docute.js.org/#/home?id=installation) werden. Daraufhin kann mit dem Befehl `docute ./` ein lokaler Server gestartet werden, welcher im Browser über https://localhost:8080 einsehbar ist.

<br><br>
Die Navigationsleiste am oberen Rand basiert auf dem docute.init() Skript welches in index.html zu finden ist.
<br>
Beim Zufügen einer neuen Folie ist diesem Skript ein neuer Link anzuängen. Das Format lässt sich hierbei aus den existierenden Beispielen entnehmen.
