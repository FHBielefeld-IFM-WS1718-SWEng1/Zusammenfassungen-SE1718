## Systemanalyse mit Analyseklassendiagrammen

**Autoren:**

 Jendrik Müller, Patrick Poppe

### Klassendiagramme

![Klassendiagramm](vorlesung8/Bilder/Klassendiagramm.png)

In einem Klassendiagramm gibt es unterschiedliche Elemente. 

Zum einen gibt es natürlich Klassen. Diese können auch abstrakt sein. Auf jedenfall enthalten Sie aber Attribute und Methoden, sowie einen Klassennamen. Zwischen den Klassen bestehen Beziehungen. Diese werden Assoziationen genannt. Was genau Assoziationen sind, wird später noch geklärt. In dem Diagramm werden an den Assoziationen jedoch auch Namen und Multiplizitäten geschrieben. Diese beschreiben die Beziehungen genauer. 

Grafisch wird das dann so dargestellt:



![Klassendiagramm mit den Elementen](vorlesung8/Bilder/Klassendiagrammobjekte.png)

#### Sichtbarkeiten

Für die Atrribute und Methoden werden zusätzlich noch Sichtbarkeiten mit angegeben. Ein "+" bedeutet public und heißt, dass dies für alle Elemente sichtbar ist.  Ein "-" kennzeichnet das Attribut als private, heißt es ist nur für Instanzen dieser Klasse sichtbar. Die "#" bedeutet protected und kennzeichnet das Attribut für alle Instanzen des Objektes und abgeleitete Instanzen als sichtbar. Der Defaultwert, welcher auch verwendet wird, wenn nichts angegeben wird, ist jedoch "~" (package). Dann ist das Attribut für alle objekte im gleichen Paket sichtbar.



Abgeleitete Attribute werden mit einem "/" vor dem Namen dargestellt. Die Sichtbarkeit kann zusätzlich angegeben werden. 

Abstrakte Klassen und Methoden werden kursiv geschrieben.

#### Generalisierung

![Diagramm zur Generalisierung](vorlesung8/Bilder/generalisierung.png)

In dem Diagramm sieht man die Vererbungsidee. Je mehr Klassen von einer Klasse erben, destso generalisierter, also allgemeiner, ist sie. Erbt eine Klasse von vielen anderen Klassen zuvor, ist sie spezialisiert.



Mehrfachvererbung ist in UML-Diagrammen zulässig.



![Klassendiagramm mit den Elementen](vorlesung8/Bilder/vererbung.png)

In diesem Diagramm sieht man ebenfalls noch einmal ein Beispiel für Vererbung. Die abstrakte Klasse "Message", erkennbar am kursiven Klassennamen, implementiert das Interface "Serializible". Die drei Unterklassen wiederum erben von der Klasse "Message".



#### Stereotypen

Über dem Klassennamen können noch verschiedene Stereotypen angegeben werden. Diese können dann bei der Umsetzung des Diagrammes speziell behandelt werden. Dies können zum Beispiel "interface" oder "enumeration" sein. Stereotypen werden in doppelten spitzen Klammern angegeben.



#### Merkmale

![Klassendiagramm mit den Elementen](vorlesung8/Bilder/merkmale.png)

Ein Merkmal wird normalerweise in der Form {name = wert} notiert. Eigene Merkmale können für Klassen und Attribute definiert werden.

#### Verantwortlichkeiten

Verwantwortlichkeiten sind die Verfplichtung einer Klasse, einen Bestimmten Dienst auszuführen. Diese Verfplichtungen stehen im Klassendiagramm noch unter den Methoden, werden jedoch nur selten verwendet.

### Logisch-statische Sicht auf ein Softwaresystem mit Analyseklassendiagrammen in der Systemanalyse

#### Einordnung in den Entwicklungsprozess

![Entwicklungsprozess](vorlesung8/Bilder/entwicklungsprozess.png)

| Was                                      | Enwicklungsphase    |
| ---------------------------------------- | ------------------- |
| Beschreibungder Anwendungsfälle          | Anforderungsanalyse |
| Beschreibung der Akteure                 | Anforderungsanalyse |
| Spezifikation der Abläufe (z.B. Geschäftsvorfälle) mit Aktivitätsdiagrammen | Systemanalyse       |
| Ermitteln von Analyseklassendiagramm mit Klassen, Attribute und Beziehungen und Methoden | Systemanalyse       |





![etwickler_domain_experte](vorlesung8/Bilder/etwickler_domain_experte.png)

#### Das Domain Object Model (=Analyseklassendiagramm)

Das Analyseklassendiagramm stellt die statische Struktur eines Systems dar und illustriert wichtige Konzepte aus der reallen Welt und deren Beziehungen in der Anwendungsdomäne. Dabei soll dargestellt werden, was das System aus Anwendersicht leisten soll. Daher ist das Analyseklassendiagramm ein Modell von realen Konzepten und nicht von Software komponenten, denn es handelt sich hierbei um keine Beschreibung des Software Desingns. Es besteht aus statischen Elementen, in denen machmal Anttribute, aber keine Methoden definiert werden. Da fehler in der Analyse sehr teuer sind, muss das Analyseklassendiagramm sehr sorgfältig modelliert werden.

![Analyseklassendiagramm](vorlesung8/Bilder/analyseklassendiagramm.png)

#### Strategien, um Klassen für Analyseklassendiagramm zu finden

##### Substantivmethode

Der amerekanische Informatiker James Rumbaugh empfahl 1991die Substantivmethode zur Identifikation von Klassen. Dabei werden aus den Anforderungsdefinitionen an ein geplantes System alle Substantive markiert. Diese werden nun zu einem Glossar zusammen getragen das weiter Analysiert wird. Dabei ist jeder Eintrag ein Klassenkandidat.

##### CRC-Methode(Class, Responsibility, Collaboration)

Bei dieser Technick wird für jede potentielle Klasse eine Karteikarte angelegt, die die drei Abschnitte Klassenname, Zuständigkeit und Zusammenarbeit hat. Die Substantivmethode und die CRC-Methode können auch kombiniert werden, dabei dient die Substantivmethode zum Auffinden der Klassen und die Klasseneigenschaften werden danach mit CRC-Karten (oder einem Texteditor) beschrieben.

##### Beispiel für ein Glossar

| Eintrag        | Beschreibung                             |
| -------------- | ---------------------------------------- |
| Benutzer       | Angemeldeter "Kunde" mit Account         |
| Account        | Bei der Registrierung wird für den "Kunden" ein Account angelegt, der ihn identifiziert. |
| Profil         | Persönliche Seite, dei ein Benutzer für sich anlegen kann/muss. |
| Postfach       | Jeder Account verfügt über ein Postfach zum Empfangen und Senden von Nachrichten. |
| Präferenzen    | Eine Liste von Vorlieben, die ein Benutzer für die Suche nach anderen Benutzern anlegt |
| Präferenzliste | Eine vom System bereitgestellte Liste, die auf die Präferenzen des Benutzers zutreffende andere Benutzer anzeigt |
| Vorschläge     | Eine vom System bereitgestellte Liste mit möglicherweise für den Benutzerinteressanten anderen Benutzern. |
| Freunde        | Andere Benutzer, die der Benutzer als Freunde deklariert hat. |
| Admin          | Jemand der administrative Arbeiten am System durchführt. |
| Fakeuser       | EineArt Super-Admin, der mehrere Benutzer löschen und beliebig viele Postfächereinsehen kann. |



#### Analyseklassendiagramme - Konstruktion

Zur Konstruktion des Analyseklassendiagramms dien eine Grammatische Analyse nahand von Beschreibungen, wie zum Beispiel dem Glossar, Use-Casses-Beschreibungen, und sonstige Dokumente, des zu erstellenden Systems in natürlicher Sprache. Dabei gilt es Klassen, Attribute Assoziationen, Vererbung und Operationen zu finden.



#### Klassen

Der Text der Anforderungen dient als Grundlage zum Finden erster Klassen. Dabei werden alle Substantive in Anforerungen und Glossar betrachtet, bei denen es sich um Klassen oder Attribute handeln kann.

| Klassen                                  | Attribute                                |
| ---------------------------------------- | ---------------------------------------- |
| komplexe Dinge                           | einfach strukturierte Dinge              |
| wichtige Eigenschaften und Fähigkeiten   | eine vorherschende Eigenschaft           |
| z.B. Personen, Gegenstände, Bestellungen | z.B Name einer Person, Farbe eines Gegenstandes, Datum einer Bestellung |





#### Instanzvariablen und Methoden

Auf Eigenschaften, sprich Instanzvariablen, wird durch Adjektive und auf Operadionen duch  Verben hingewiese. Nun müssen den Instanzvariablen noch geeignete Datentypen zugewiesen werden, wobei man bei komplexeren Instanzvariablen auch Klassen als Typ verwenden kann. Man muss darauf achten, dass die Instanzvariablen keine Implementierungs- und Entwurfdetails beschreiben und, dass die Methoden und Instanzvariablen eine Sichtbarkeit enthalten. Im zu analysierenden Text können auch Objekte identifiziert werden, die zur Veranschaulichung in einem Objektdiagramm dargestellt werden können. 



#### Assoziation

Zur Bestimmung einer Assoziation ist zunächst die Kardinalität und die Rolle der beteiligten Klassen zu beachten. Zusätzlich ist noch die Richtung und Navigierbarkeit der Assoziation zu beachten und man muss Assoziationen und Rollen bennenen. Abschließend muss man noch festlegen, was für eine Art von Beziehung(Aggregation oder Komposition) vorliegt und ob die Kardinalitäten 0..* oder 0..* sind.

#### Vererbung 

Wenn Objekte verschiedener Klassen große Gemeinsamkeiten haben, kann Vererbung genutzt werden. Dazu bildet man aus den gleichartigen Klassen eine neue Oberklasse.

Prüfen auf gute Vererbung:

- [ ] das Verständnis des Modells wird verbessert
- [ ] es liegt eine "is-a"-Beziehung vor
- [ ] Maximal drei bis fünf Hierarchiestufen
- [ ] Vererbung ist sinnvoller als Komposition



### Best practices

#### Klassendiagramme Best practices

- Weniger ist mehr: nur das Notwendige.Verständlich für den Auftraggeber
- Gute Analysenklassendiagramme besitzen folgende Merkmale:
  - Klassen repräsentieren die fachlichen Konzepte der Anwendungsdomäne
  - Keine Entwurfs- oder Implementierungsdetails
  - Nicht aus jedem Detail eine Klasse modellieren
- Aussagefähige Klassenname: Substantiv im Singular
- Keine überkreuzenden Assoziationslinien
- Orthogonalität: Nur gerade (horizontal, vertikal)Assoziationslinien
- Oberklassen nach oben
- Fachlich hängt die grafische Benutzeroberfläche (GUI, Graphical User Interface) eng mit dem unterliegendem Geschäftsklassenmodell zusammen
- Möglicher Ansatz: „Mache alle Objekte an der Oberfläche sichtbar, die ein Nutzer ändern oder für dessenInhalte er sich interessieren kann.“



### Beispiel 1

#### Anforderungen

- In einer Hochschulverwaltung sind mehrere Personengruppen tätig.
- Die Hochschule hat Angestellte, die Professoren, Labor-Ingenieure, Lehrbeauftragte, Sekretärinnen oder Tutoren sein können. 
- An einer Hochschule studieren Studenten, die auch als Tutoren in einzelnen Lehrveranstaltungen eingesetzt werden können.
- Jede Person hat einen Namen, Geburtsdatum und Geburtsort. 
- Alle Angestellten verfügen über ein Gehaltskonto.
- Dozenten haben einen akademischen Titel und leisten pro Semester eine bestimmte Anzahl Semesterwochenstunden (SWS).
- Jeder Student hat eine identifizierende Matrikelnummer.



Zur Identifizierung der Klassenkadidaten werden nun alle Substantiver markiert und zu einem Glossar zusammengetragen. Alternativ reich hierbei auch das Zusammentragen zu einer einfachen Liste, wobei beim Erstellen eines Glossars deutlicher auffällt, welche Substantive redundant, irrelevant oder Attribute sind und wie die Beziehung unter ihnen ist.



| Eintrag               | Beschreibung                             |
| --------------------- | ---------------------------------------- |
| Hochschulverwaltung   | besteht aus mehreren Personenguppen      |
| Personengruppe        | gruppierung von Personen                 |
| Hochschule            | hat Angestellte                          |
| Angestellter          | arbeiter an einer Hochschule und lässt sich in verschiedene Gruppierungen unterteilen |
| Professor             | ist eine Art von Angestellter an einer Hochschule, mit einem akademischen Titel |
| Labor-Ingenier        | ist eine Art von Angestellter an einer Hochschule |
| Lehrbeauftragter      | ist eine Art von Angestellter an einer Hochschule, mit einem akademischen Titel |
| Sekretärinn           | ist eine Art von Angestellter an einer Hochschule |
| Tutor                 | ist eine Art von Angestellten an einer Hochschule, bei dem es sich gleichzeitig auch um einen Studenten handeln kann |
| Student               | studierender an einer Hochschule         |
| Person                | ist ein Student oder Angestellter        |
| Name                  | Benennung einer Person                   |
| Geburtdatum           | Tag der Geburt einer Person              |
| Dozent                | ist ein Angestellter, der einen akademischen Titel hat |
| Titel                 | Namenszusatz eines Dozenten              |
| Semester              | sechs Monate                             |
| Anzahl                | Zahl oder Menge von etwas                |
| Semesterwochenstunden | kurz SWS, ein Dozent muss diese leisten  |
| Matriekelnummer       | identifiziert einen Studenten            |



Als nächstes folg die Eliminierung der Begriffe, bei denen aufgefallen ist, dass sie refundant oder irrelevant sind:

- Hochschulverwaltung, Personengruppen, Hochschule, Semester, Anzahl

Die folgenden Begriffe werden als Klassenkandidaten eliminiert, weil sie Eigenschaften (Attribute) anderer Substantive (Klassenkandidaten) bezeichnen:

- Namen, Geburtsdatum, Geburtsort, Gehaltskonto, Titel, Semesterwochenstunden, Matrikelnummer.

Aus diesen Informationen kann man nun eine Tabelle der Klassen und ihrer Attribute erstellen, wobei zu beachten ist, dass in dieser Projektphase der Analyse noch nicht für alle Klassen die Attribute vorliegen. Deswegen werden die Attribute für diese Klaasen zunächst noch offen gelassen und in späteren Projektphasen ergänzt. Hierbei handelt es sich um einen iterativen Entwicklungsprozess.

| Klasse              | Attribute                      |
| ------------------- | ------------------------------ |
| Person              | Name, Geburtsdatum, Geburtsort |
| Student             | Martikelnummer                 |
| Angestellter        | Gehaltskonto                   |
| Tutor               |                                |
| Dozent              | Titel, Semesterwochenstunden   |
| Sekretärin          |                                |
| Labor-Ingenieur     |                                |
| Professor           |                                |
| Lehrbeauftragter    |                                |
| Studentischer Tutor |                                |



Abschließend lässt sich das folgende Klassendiagramm erstellen:

![Klassendiagramm](vorlesung8/Bilder/Beispiel1_Klassendiagramm)