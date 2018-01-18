# Kapitel 14 Implementierung und Dokumentation 

**Autor: **  
André Matutat



## Lernziele

- Wissen, was die Ziele der Implementierung sind
- Verstehen, wie UML-Diagramme in Software umgesetzt werden
- Code Smells und schlechtes Exception Handling identifizieren und beheben können

## Ziel der Implementierung 

- Ausgangspunkt: Entwurfsspezifikation mit System- und Softwarearchitektur
- Transformation der Entwurfsergebnisse in Software, die auf einem bestimmten Zielrechner ausführbar ist
- Konsistenz mit dem Entwurf: Strukturen des Entwurfs lassen sich im Source Code leicht wieder finden
- Schnittstellen des Programmsystems sind explizit beschrieben
- Ergebnis: Software, Dokumentation, Entwicklertests

**Die Erfüllung der Eigenschaften ist abhängig von**
- der Art der Programmiersprache und Programmierkonzepte (z.B. objektorientiert)
- Der kompetentz der Beteiligten (z.B. des Software-Entwicklers)

## Übersetzen von UML Klassendiagramme in objektorientierte Programmiersprachen 

![](vorlesung14/bilder/bild1.png)
- Bei Übersetzung in Source-Code auf Vererbung und Sichtbarkeit achten
- Es kann vereinbart werden, dass get- und set-Methoden in Klassendiagrammen weggelassen werden


### Statische Strukturen 
![](vorlesung14/bilder/bild2.png)
- **Attribute mit package-scope („~“)**
 ```java
 Klassendiagramm mit Klasse „A“ und Attribute i: 
~ int i; 

Java Source Code:
public class A { 
  int i;
}
 ```



- **abgeleitete Attribute („/“)** 
```java
  //Klassendiagramm mit Klasse „A“ und Attribute „enthalteneMehrwertSteuer“: 
  // double enthalteneMehrwertSteuer; 
  //In einer Klasse „A“ wird umgesetzt zu
  public class A {  
 	 static double mwst = 19;
  	double preis;
  	public getEnthalteneMehrwertSteuer() {
  		return preis - (preis / (1 + (mwst/100))); 
 	 } 
  }
```

### Beziehungen

![](vorlesung14/bilder/bild3.png)

- Bei Übersetzung von Aggregation, Komposition auf Richtung und Kardinalitäten achten 

  ![](vorlesung14/bilder/bild25.png)

- Objektreferenz darf nie *null* sein. Also bei der Deklaration der Instanzvariable oder im Konstruktor setzen

  ![](vorlesung14/bilder/bild26.png)
```java
  public  class  Projektaufgabe  {
 	 private  Mitarbeiter  bearbeiter;
 	 
  	public  Mitarbeiter  getBearbeiter()  {
  		return  bearbeiter;
	}
	 public  void  setBearbeiter(Mitarbeiter  bearbeiter)  {
		 this.bearbeiter  =  bearbeiter;
	 }
}
```
![](vorlesung14/bilder/bild4.png)

### 1:1 Assoziation 

![](vorlesung14/bilder/bild5.png)

- Die entsprechende Rollen werden als Attribute in die jeweils gegenüberliegende Klasse eingefügt
- Ist die Multiplizität 0..1, kann das entsprechende Attribut unter Umständen auch den Wert *null* haben

### Kardinalität n 

- Umsetzung als Collection (Array, Container)

  ![](vorlesung14/bilder/bild6.png)

- Umsetzung hängt von Art der Collection ab

  - Sollen Daten geordnet werden?
  - Sind doppelte Einträge erlaubt?
  - Gibt es spezielle Zuordnung key-> value?

- Multiplizitäten 0..7 ist als Array umsetzbar

- Eine mögliche Umsetzung für 1..* sieht wie folgt aus: 
```java
public class Projektaufgabe {
  	private List<Mitarbeiter> bearbeiter= new ArrayLIst<Mitarbeiter>();
  	...
}
```

![](vorlesung14/bilder/bild7.png)

### Assoziation vs. Aggregation vs. Komposition

![](vorlesung14/bilder/bild8.png)

```java
public class A {
  public voud doSomething(B b){
    
  }
}
```
```java
public class A {
  private B b;
  public void setB (B b){
    this.b=b;
  }
}
```
```java
public class A {
  private B b=new B();
}
```

### Arten der Zugehörigkeit (Komposition)

- Existenz abhängiges Teil, Instanzvariable gehört ausschließlich zum Objekt.
- Bei Rückgabe wird Kopie des Objekts erstellt und zurückgegeben

![](vorlesung14/bilder/bild9.png)
```java
public class Projektaufgabe {
   private final Mitarbeiter bearbeiter;
   public Mitarbeiter getBearbeiter() { 
     return bearbeiter.clone();
   }
       
}
// in Mitarbeiter.java
public Mitarbeiter clone() {
 Mitarbeiter ergebnis = new Mitarbeiter(); 
 ergebnis.minr = minr; 
 ergebnis.nachname = nachname; 
 ergebnis.vorname = vorname; 
 return ergebnis;
}
```

![](vorlesung14/bilder/bild10.png)
``` java
class Customer {
  private String name;
  private BankAccount account;
  
  public Customer (String cname, double initalBalance){
    name=cname;
    account =new BankAccount(initialBalance);
  }
  public String getName(){
   return name;
 }
 public double getBalance(){
   return account.getBalance();
 }
 public void transferTo(BankAccount other, double amount){
   account.transfertTo(other,amount);
 }
 public void withdraw (double x){
   account.withdraw(x);
 }
 public void deposit(double x){
   account.deposit(x);
 }
}
```
![](vorlesung14/bilder/bild11.png)

```java
import java.util.ArrayList;
class Customer {
  private String name;
  private ArrayList accounts;
  
  public Customer(String cname){
    name=cname;
    account=new ArrayList();
  }
  public void ceateAccount (double initialBalance){
    BankAccount a=new BankAccount(initialBalance);
    accounts.add(a);
  }
  public String getName(){
    return name;
  }
}
```
- Eine weitere Möglichkeit, Komposition umzusetzen, ist die Verwendung einer inneren Klasse



![](vorlesung14/bilder/bild12.png)

![](vorlesung14/bilder/bild13.png)

## Beispiel Übersetzung 

### ...das gesamte Diagramm

![](vorlesung14/bilder/bild14.png)

### Übersetzung nach Java: Klassen (1/2)

![](vorlesung14/bilder/bild15.png)

- Erstellung einer konkreten Instanz oom:  *Lehrveranstalung oom= new Lehrveranstaltung( "Objektorientierte Midellierung",394,3);*
- Zugriff auf Attribut name: *oom.name;*

###Übersetzung nach Java: Klassen (2/2)

![](vorlesung14/bilder/bild16.png)

- Erstellung einer Instanz oom: wie vorher

- Zugriff auf Attribut name: *oom.getName();*

  ​

### Übersetzung nach Java: Abstrakte Klasse

![](vorlesung14/bilder/bild17.png)

### Übersetzung nach Java: Generalisierung

![](vorlesung14/bilder/bild18.png)

- Neue Instanz: *wma1= new WissenschafterlMA(123,"abc","abc@xyz.at","Informatik");* 
- Zugriff auf name= *wma1.name;*

###Übersetzung nach Java: Klassenvariable

- Angabe: Die Anzahl der Mitarbeiter ist bekannt

- Realisierung: Klassenvariable

  ![](vorlesung14/bilder/bild19.1.png) ![](vorlesung14/bilder/bild19.2.png)

  - Wird eine Klasse, die von Mitarbeiter erbt, instanziert, wird *anzahl* um 1 erhöht
  - Durch *Mitarbeiter.anzahl* oder *Wissenschaft1Ma.anzahl* oder *wma1.anzahl* bekommt man die Anzahl der Mitarbeiter

###Übersetzung nach Java: 1:1-Assoziation

![](vorlesung14/bilder/bild20.png)

- Die entsprechenden Rollen werden als Attribute in die jeweils gegenüberliegende Klasse eingefügt
- Ist die Multiplizität 0..1, kann das entsprechende Attribut unter Umständen auch den Wert *null* haben,

### Übersetzung nach Java: Unidirektionale ?:1-Assoziation

![](vorlesung14/bilder/bild21.png)

- Keine Änderung an Vortragender!
- Viel leichter zu implementieren als bidirektionale Assoziation

### Übersetzung nach Java: Bidirektionale 1:*-Assoziation

![](vorlesung14/bilder/bild21.png)

- Lehrveranstaltung wird wie vorher implementiert
- Wenn *n* fix vorgegeben ist (nicht *) , dann kann auch ein Array verwendet werden

### Übersetzung nach Java: Starke Aggregation

![](vorlesung14/bilder/bild22.png)

- Nun müssen die Operationen, die auf den Instituten durchgeführt werden können, durch die Fakultät zur Verfügung gestellt werden


### Übersetzung nach Java: Schwache Aggregation

- Bei einer starken Aggregation unterliegt der Lebenszyklus der Teilobjekte dem „Ganz-Objekt“. Das heißt, die Teilobjekte werden vom „Ganz-Objekt“ erzeugt.
- Bei einer schwachen Aggregation können die Objekte außerhalb des „Ganz-Objekts“ erzeugt werden und zum Beispiel im Konstruktor übergeben werden.

### Übersetzung nach Java: Assoziationsklasse

![](vorlesung14/bilder/bild23.png)

- Die Assoziation wird mit Hilfe einer Hashtable abgebildet
- Ist die Assoziation nicht gerichtet, muss in der gegenüberliegenden Klasse ebenfalls eine Hashtable eingefügt werden

## Best Practices

### Problem 

- Software wird verändert und erweitert
- Die Personen, die an der Software arbeiten, ändern sich
- Wissen über die Software befindet sich oft nur in den Köpfen der Personen
- Die Wartungsphase ist die längste Phase im Softwarelebenszyklus
- Software muss daher verständlich sein und auch bleiben
- Sinnvoll ist daher die Beachtung von **Best practices** 

### Best practices

- Vermeiden Sie trickreiche Programmierung.
  - Kein Zeichen von Intelligenz
  - Dient nicht der Arbeitsplatzsicherung 


- Software ist zuerst ein Mittel zur Kommunikation mit Entwicklern und dann erst ein Mittel zur Kommunikation mit dem Computer
- Zuerst funktional korrekt,dann effizient implementieren. 

  - Make it work.

  - Make it right.

  - Make it fast.
- Ohne(„High-Level“)-Dokumentation ist ein Programm nur wenig wert
- Vermeiden Sie tiefgeschachtelte Kontrollstrukturen (if,while,for,...)
- Es ist möglich,in Programmiersprachen,die die strukturierte Programmierung unterstützen,schlechte Programme zu schreiben
- Entwickler sind gut oder schlecht, unabhängig von der verwendeten Programmiersprache
- Trotz TDD: erst denken,dann programmieren,dann compilieren

### Namenswahl bei der Benennung von Objekten und Operationen

- Aussagekräftige, konsistente Namen,auch wenn die Bezeichner langwerden
- Namen von Klassen, Methoden und Attributen sollten aussprechbar sein, also vermeiden Sie Namen wie chtoghk. 
- Nur allgemein gebräuchliche Abkürzungen verwenden
  - Schlechtes Beispiel: WPSMH=Wärmepumpensteuerung
- Der Typ eines Wertes sollte nicht im Namen einer Variable oder Methode enthalten sein. Es kann zu Verwirrungen kommen, wenn sich der Typ ändert. 
- Konsistente Namen: Verwenden Sie immer den selben Namen für die gleiche Absicht. (z.B immer size, anstatt hin und wieder mal das Wort length oder amount zu verwenden.)  
- Keine Sprachmischung  (denglisch). Entweder englisch, oder deutsch
- Groß-/Kleinschreibung
  - große Anfangsbuchstaben für Datentypen, Klassen
  - kleine Anfangsbuchstaben für Operationen und Variablen
- Anhand des Namens sollte direkt erkennbar sein, welchen Zweck eine Methode, Klasseund Attribut hat
  - Hauptwörter für Werte, z.B. „breite“
  - Zeitwörter für Tätigkeiten, z.B. „readKey“
  - Eigenschaftswörter für Bedingungen, z.B. „gueltig“

### Gebrauch von Kommentaren

- Kurze und präzise Beschreibung des Wesentlichen
- Nicht jede Methode (z.B. get-Methode) einer Klasse muss mit einem Kommentar versehen werden
- Jede Klasse soll mit Kommentaren beschrieben werden
- Erläuterungen der Bedeutung von Variablen
- Erläuterung abgeschlossener Teilaufgaben(Programmblöcke)
- Erläuterung schwer verständlicher Anweisungen
- Bei Änderungen am Source-Code müssen die Kommentare ebenfalls geändert werden

## Software Dokumentation

### Ziel der Dokumentation

- Eine Softwareprodukt ist nur so gut, wie seine Dokumentation
- Die Dokumentation unterstützt den gesamten Softwareentwicklungsprozess einschließlich des Betriebs und der späteren Wartung des Softwareprodukts

| Phase                   | Beschreibung                             |
| ----------------------- | ---------------------------------------- |
| Während der Entwicklung | Kommunikation zwischen beteiligten Personen |
| Nach der Entwicklung    | Unterstützung beim Einsatz und der Wartung der Software |
| Zukünfige Projekte      | Dokumentation des Projektverlaufs zur besseren Planung neuer Produkte sowie der Wiederverwendung von Lösungen |

- Die Dokumentation verfolgt unterschiedliche Ziele. Deshalb gibt es diverse Dokumentationsarten, die auf verschiedene Nutzergruppen ausgerichtet sind:

| Art                   | Beschreibung                             |
| --------------------- | ---------------------------------------- |
| Benutzerdokumentation | Kommunikation zwischen beteiligten Personen |
| Systemdokumentation   | Entwickler des Softwareprodukts und Personen, die mit den Änderungen und Erweiterungen beschäftigt sind |
| Projektdokumentation  | Manager des Softwareprojekts             |

### Benutzungsdokumentation

- Benötigte Hardware- und Softwareressourcen
- Angaben über Durchführung und Voraussetzungen der Installation der Software
- Zweck des Softwaresystems und Beschreibung der Funktionalität
- Typische Anwendungsbeispiele für alle Systemfunktionen
- Zusammenstellung der Fehlermeldungen und Hinweise auf Fehlerursachen und Maßnahmen zur Fehlerbeseitigung

### Systemdokumentation

- Beschreibung aller Einzelheiten des Aufbaus eines Softwaresystems, der Struktur der einzelnen Softwarebausteine und der Testaktivitäten
- Anforderungsspezifikation, Analyseergebnisse, Entwurfsergebnisse, Testprotokollierung
- Testplan für den Integrations- und den Abnahmetest

### Projektdokumentation

- Projektplan mit dem geplanten Zeitrahmen und Personalzuteilung, Angabe über Ergebnissen,die nach jeder Phase vorliegen sollen
- Definition des Projektstandards; Vorgabe von Konventionen für die Dokumentation
- Verzeichnis über die verbrauchte Arbeitszeit, Ressourcen und sonstige Aufwendungen
- Projekttagebuch zur Protokollierung der Besprechungen von Projektmitarbeitern, Informationen über Entscheidungen mit entsprechender Begründung

