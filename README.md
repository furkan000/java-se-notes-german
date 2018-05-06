# Java

## Objekte

Objekte erstellen:

    Klassenname objektName = new Klassenname();

Alternativ:

    Klassenname objektName;
    objektName = new Klassenname(); 

**toString**
Beispiel:

    public class Person {
        public String toString() {
            return this.name + ", age " + this.age + " years";
        }
    }


    public static void main(String[] args) {
        Person bob = new Person("Bob");
        System.out.println( andy ); //same as System.out.println( andy.toString() ); 

**this**

- this wird anstelle des Namens der aktuellen Klasse benutzt (in der “this” steht)
## Attribute
- Eigenschaft die einem konkreten Objekt/Klasse zugeordnet ist
- Wird oben in der Klasse angelegt

Auf Attribut eines Objektes zugreifen: 

    Klassenname.attribut //Papagei.name = null;
## Konstruktor
- Zum setzen der Werte von Attributen während der Objekterzeugung
- Ein leerer (Standard-) Konstruktor ohne Parameterübergabe, wird vom Compiler automatisch erzeugt


- Sie tragen immer den Namen der Klasse
- Sie besitzen keinen Rückgabewert
- Sie können überladen werden
- Sie können Objekte erzeugen

Beispiel Klasse:

    public class KonstruktorClass { 
      private int x;
      
      // Standardkonstruktor muss nicht angegeben werden 
      public KonstruktorClass() {} 
      // zweiter Konstruktor 
      public KonstruktorClass(int i){ 
        this.x=i; 
      } 
    }

Beispiel Objekterzeugung:

    KonstruktorClass konst = new KonstruktorClass();
    //oder
    KonstruktorClass konst = new KonstruktorClass(2);

**Effektives überladen von Konstruktoren**

    public Person(String name) {
        this(name, 0);  
        // run here the other constructor's code and set the age parameter to 0
    }
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
        this.weight = 0;
        this.height = 0;
    }


## Methoden

Methode ohne Rückgabewert:

    void sagHallo(){System.out.println("Hallo")}

Methode mit Rückgabewert:

    String sagHallo(){return "Hallo"}

Methodenaufruf:

    objektName.methodenName();


- Die Ausführung einer Methode wird gestoppt, wenn der return-Befehl ausgeführt wird


- Innerhalb einer Methode (z. B. `public static void main(String[] args)` ) kann keine neue Methode erzeugt werden 


- Primitive Datentypen **außerhalb der Klasse** einer Methode kann nicht durch diese ihren Wert ändern, auch nicht wenn sie als Parameter übergeben worden sind.
  - Bei Objektdatentypen (z.B. ArrayList) führt eine Änderung an z. B. einer bereits vorhandenen ArrayList, die einer Methode **durch einen Parameter übergeben** wurde dazu, dass sie überall verändert wird
![](https://raw.github.com/UniversityHelsinkiTKTL/MOOC-material/master/img/metodi1.png)
![](https://raw.github.com/UniversityHelsinkiTKTL/MOOC-material/master/img/metodi-lanka.PNG)


**Überladen von Methoden** 
Gleichen Methodenname mehrfach in einer Klasse verwenden

- Unterschiedliche Parameterliste entscheidend
- Rückgabetyp, Parameternamen nicht entscheidend

Beispiel effektives Überladen einer Methode:

    public void becomeOlder() {
        this.becomeOlder(1);
    }
    
    public void becomeOlder(int years) {
        this.age = this.age + years;
    }
## Parameter 
- Werte die einer Methode übergeben werden
- Für jeden definierten Parameter muss ein Wert übergeben werden
- Die Reihenfolge und der Datentyp müssen stimmen


- Der Name des Parameters ist egal!
- Eine ArrayList kann auch ein Parameter sein

Beispiel Methode

    public void sag(String aussage, String zweiteAussage){
      System.out.println(aussage + zweite Aussage);
    }

Beispiel Methodenaufruf:

    objekt.sag("Hallo ", "Welt")
## Getter und Setter (Accessor-) Methoden
- Mit Getter und Setter Methoden können Attribute außerhalb der Klasse gelesen und beschrieben werden.
- Getter und Setter sind wichtig für die Rechteverwaltung.

Beispiel:

    public String getName(){
      return name;
    }
    public void setName(String name){
      this.name = name;
    }
## Sichtbarkeit

Die Faustregel ist, dass Methoden zumeist public, Attribute dagegen als private deklariert werden.

                | Class | Package | Subclass | Subclass | World
                |       |         |(same pkg)|(diff pkg)| 
    ————————————+———————+—————————+——————————+——————————+————————
    public      |   +   |    +    |    +     |     +    |   +     
    ————————————+———————+—————————+——————————+——————————+————————
    protected   |   +   |    +    |    +     |     +    |         
    ————————————+———————+—————————+——————————+——————————+————————
    no modifier |   +   |    +    |    +     |          |    
    ————————————+———————+—————————+——————————+——————————+————————
    private     |   +   |         |          |          |    
## Bedingungen und (logische) Operatoren:

Bedingungen und logische Operatoren liefern true oder false als Ergebniss.
****
- if (Bedingung){Anweisung};
- && (Und)
- || (Oder)
- > ; < ; >= ; <= (Größer, Kleiner, Größer gleich, Kleiner gleich)


- == (Gleich), != (Ungleich) 
  - Strings und Objektdatentypen müssen über equals verglichen werden:
    "Hallo".quals("Hallo") //True

**Equals**

- equals ist eine Methode der Klasse object und prüft, ob zwei Objekte die gleiche Referenz haben (ausnahme String!)
- d.h. eine Objekt und eine identsiche Kopie dieses Objekts würden zusammen `false` zurückgeben (ausnahme String!)
- Die Klasse String überschreibt die Methode equals

**Arithmetische Operationen abkürzen:**

    length += 10;   // same as length = length + 10;
    length *= 10;   // same as length = length * 10;
    length /= 10;   // same as length = length / 10;
    length %= 10;   // same as length = length % 3;


## Schleifen
    while(Bedingung){Anweisung}
    do{Anweisung}while(Bedingung);
    for (int i = 0; i < 10; i++){Anweisung}

**Break**
Mit dem break-Befehl wird die Schleife komplett beendet. Der Programmfluß setzt hinter dem Schleifenrumpf wieder ein.
**Continue**
Der continue-Befehl beendet nur den aktuellen **Schleifendurchlauf**. Bei while und do-while wird als nächstes die Schleifenbedingung getestet. Bei for wird zuerst die Laufvariablen-Manipulation durchgeführt und dann die Bedingung getestet.

## Arrays

Unter Array versteht man ein Feld oder Container, das in der Lage ist, mehrere Objekte vom gleichen Typ aufzunehmen und zu verwalten. Dabei wird der Inhalt mit einem Index durchnummeriert, das erste Element hat dabei den Index = 0.


- Feste Größe
- Löschen von Elementen ist ohne weiteres nicht möglich

Anlegen/Deklaration:

    Typ[] Name = new Typ[Anzahl]; //String[] papageienNamen = new String[4];

oder

    Typ Name[] = new Typ[Anzahl];

Zugriff:

    System.out.println(papageienNamen[0]);

Initialisierung:

    variablenName[index] = wert; //papageienHaus[0] = new Papagei("Polly");

Deklaration und Initialisierung in einem Schritt:

    Typ[] variablenName = {wert1, wert2, …};

Größe des Arrays:

    Attribut length (arrayName.lenght)
## Vererbung

Superklasse verebt an Subklasse: Methoden, Attribute

- Methoden und Attribute können überschrieben werden (auch von höheren Oberklassen).
- Methoden und Attribute können ergänzt werden.

In die Variable einer Oberklasse kann ein Objekt vom Typ einer Unterklasse gespeichert werden:

    Vogel vogel;
    vogel = new Ente();
## Polymorphie
    Person olli = new Student("Olli", "Ida Albergintie Street 1 00400 Helsinki");
    olli.credits();        // NOT WORKING!
    olli.study();              // NOT WORKING!
    String.out.println( olli );   // olli.toString() IT WORKS!

Wenn eine Variable verschiedene Typen akzeptiert, so können nur die Methoden benutzt werden die von allen definiert sind.

Wenn das der Fall ist: Aufrufen einer Methode ruft die speziellste Methode auf

- Hätte Person auch die Methoden credits/study, so würden die Methoden vom Studenten anstelle der Person aufgerufen, da es die speziellere Methode ist


## Typecasting 

Konvertieren in Unterklasse

- Casting zwischen Unterklassen ist nicht möglich
- Es wird zwischen impliziten und explizitem Typecasting unterschieden

Beispiel (Explizit):

    int wert;
    double wert2 = 30.5;
    wert = ( int ) wert2;
    System.out.println(wert); // Ausgabe: 30

**String -> Zahl**

    double x = Double.parseDouble("1.23")
    int y = Integer.parse("123")
    ...
## Collections
- Sammlungen akzeptieren Elemente beliebiger Objektdatentypen (primitiven Datentypen, Wrapper werden implizit gecastet)
  - zugrundeliegender Datentyp: Object
- Generics funktionieren nicht mit primitiven Datentypen
- Typeinschränkung möglich

**ArrayList**
Erzeugung:

    ArrayList<Typ> sammlung = new ArrayList<>();
- `new ArrayList<>(eineSammlung);` Erzeugt eine Liste, die die Elemente der übergebenen Sammlung enthält
- Damit ArrayList funktioniert:   `import java.util.ArrayList;` oder `import java.util.*;`

 

- Array mit veränderlicher Größe (dynamisch)
- Schneller Zugriff auf Elemente an beliebiger Position
- Stellt Methoden zur Verwaltung zur Verfügung:
  - add – Hinzufügen eines Elements
  - addAll – Hinzufügen einer anderen Sammlung
  - contains – Prüfen ob ein Element enthalten ist
  - get - Zugriff auf Element
  - remove - Element löschen; Achtung bei int ,“Integer.valueOf” benutzen
  - size - Ermittelung der Größe

Beispiel Zugriff:

    arrayList.get(0);


- Eine ArrayList kann auch ein **Parameter** sein, dabei ist der Name egal!
- Ein ArrayList kann auch der **return-Wert** einer **Methode** sein

**Collections-Package**

- Damit Collections funktioniert: `import java.util.Collections;` oder `import java.util.*`

Methoden:

- sort - Sortiert alphabetisch
- shuffle - Mischt
- reverse - Invertiert Reihenfolge

Beispiel:

    Collections.sort(teachers);

**Foreach**

- Anwendbar auf Sammlungen und einfache Arrays

Beispiel:

    for (ArrayDatentyp bezeichner : arrayName){ //Für jedes Element in Sammlung
      System.out.println(bezeichner);
    }

**LinkedList**

- gleichen Methoden wie ArrayList
- Listenelemente stehen in Verbindung zum jeweiligen Vorgänger bzw. Nachfolger
- Elemente können schneller hinzugefügt und gelöscht werden 

| ArrayList | LinkedList |
|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| Direkter Zugriff über Index möglich<br />– get(int index) | Durchlaufen aller vorherigen Elemente notwendig<br />– get(int index) |
| Hinzufügen von Elementen im vorderen Bereich ist teuer<br />– add(int index, E element) | Hinzufügen von Elementen im vorderen Bereich ist günstig<br />– add(int index, E element) |



![](https://i.stack.imgur.com/skN72.png)


**HashMap**
Eine Map ist wie ein Wörterbuch aufgebaut. Jeder Eintrag besteht aus einem Schlüssel (key) und dem zugehörigen Wert (value). Es können beliebige Objekte hinzugefügt oder entfernt werden. Jeder Schlüssel darf in einer Map nur genau einmal vorhanden sein, wodurch jedes Schlüssel-Wert-Paar einzigartig ist.

    HashMap<String,String> map = new HashMap<>();
    numbers.put("One", "Yksi"); //die put() methode fügt Werte hinzu
    System.out.println(numbers.get("Two")); 
    //wird der gesucthe Wert nicht gefunden wird null zurückgegeben

**HashSet**
Eine Menge (Sets) ist eine (erst einmal) ungeordnete Sammlung von Elementen.
In der Klasse *HashSet* gibt es keine Methode, um auf ein Objekt innerhalb des Sets auf direktem Wege zuzugreifen. Um dies zu realisieren, benötigen wir einen sogenannten Iterator (zum schrittweise durchlaufen)).

## Liste mit Methoden

**Random**

    import java.util.Random;
    Random randomizer = new Random();
    System.out.println(randomizer.nextInt(10)); //Zufallszahlen von 0-9
## Strings

Strings sind unveränderbar.

## Blocks
- Blocks sind gekennzeichnet durch {…}
- Besitzen die Eigenschaft, dass Variablen die innerhalb dieser erstellt werden auch nur innerhalb dieser existieren
- Jedoch können Variablen die außerhalb definiert sind bearbeitet werden
## Modifizierer

**final**

- Mit final kann etwas (z.B. Variablen) nicht verändert werden, sie sind Konstant
  - Die Schreibweise einer konstanten Variable ist wie folgt: `CAPITAL_LETTERS_AND_UNDERLINE_CHARACTERS`

**abstract**

- Abstrakte Klassen werden benutzt wenn die Klasse nur als Oberklasse in einer Vererbungshierarchie existieren soll
- Abstrakte Klassen lassen sich nicht instanziieren, d.h. es lassen sich keine Objeke von ihr erzeugen
  - Der Modifizierer abstract sollte aber dazu nicht eingesetzt werden. Besser ist es, die Sichtbarkeit des Konstruktors auf private oder protected zu setzen.
- Abstrakte Klassen enthalten nur abstrakte Methoden
- Abstrakte Methoden können nur von Unterklassen implementiert werden

**static**

- Methoden die nicht an Objekte gebunden sind
- Können nur mit Parametern arbeiten
- Wenn die static-method von der selben Klasse aufgrufen wird dann Aufruf durch Methodenname
  - Sonst `objectName.methodName()`

**Attribute** `ClassName.variable`

- Statische Attribute gehören zur Klasse und kommen unabhängig von der Anzahl der Objekte einmal pro Klasse vor
- Weil ein statisches Attribut unabhängig von den Objekten seiner Klasse ist, kann es auch ohne Objekt existieren 

**Methoden (Klassenmethoden ≠ Instanzmethoden)** `ClassName.method()`

- Statische Methoden sind unabhängig von Objekten
- Können nur auf statische Datenelemente (Attribute) direkt zugreifen 
- Können nur andere statische Methoden aufrufen
- Können this nicht verwenden , weil es kein zugeordnetes Objekt geben kann.


- Instanzmethoden können Klassenmethoden aufrufen solange sie in derselben Klasse sind


## Binary Search
- Mit binary search kann ein Wert schneller in einem Array gefunden werden
- Es wird dabei die Menge geteilt und es wird ermittelt in welcher Hälfe der Wert liegt, bis der gesuchte Wert gefunden wurde
- Die Anzahl maximal möglicher Vergleiche kann mit dem Logarithmus zur Basis 2 berechnet werden
## Interface
- Ein Interface definiert die Methodennamen, ihre Rückgabewerte, Modifizierer
- Bsp: `public interface Readable { String read(); }`
  - Da alle Methoden in Schnittstellen automatisch abstrakt und öffentlich sind, akzeptiert der Compiler das redundante abstract und public, doch die Modifizierer sollten nicht geschrieben werden.
- Eine Klasse implementiert ein Interface wie folgt: 
  - `public class SMS implements Readable { … }`
- Interfaces können auch die Parameter festlegen
  - `public interface Comparable{ boolean greater(Object m); }`
- Wenn eine Klasse ein Interface implementiert
  - dann muss die Klasse die entsprechenden Methoden beinhalten
  - dann haben auch dei Objekte zusätzlich den Datentyp des Interfaces
- Da die in Schnittstellen deklarierten Operationen immer public sind, müssen auch die implementierten Methoden in den Klassen immer öffentlich sein.
- (Leere Interfaces sind möglich)
- Interfaces können erweitert werden, wie bei der Vererbung, siehe Bsp. unten
    interface Disgusting { double disgustingValue();}
    interface Stinky extends Disgusting {double olf();

**Abstrakte Klasse vs Interface**

- Es können mehrere Interfaces implementiert werden (, aber nur eine Klasse vererbt werden)
- Abstrakte Klassen können konkrete Methoden beinhalten
## Anwendungsbeispiel von Interfaces
    public class Printer {
        public void print(Readable readable) {
            System.out.println(readable.read());
        }
    }

**Made-Up Interfaces**

- List, Map, Set, Collections sind Interfaces
## Generics
- Der Name der Typvariablen muss in der Klassendeklaration angegeben
  - `public class Pocket<T>`
- Um die Pocket-Klasse nutzen zu könne müsse wir einen Typparameter angeben, Bsp. unten
    Pocket<Integer>  intPocket     = new Pocket<Integer>();
    //intPocket kann jetzt nur integers enthalten (im Pocket-Beispiel)
    Pocket<String>   stringPocket  = new Pocket<String>();
    //Normale Objekterzeugung im Vergleich
    Klassenname objektName = new Klassenname();


- Generic Interfaces sind auch möglich
    public interface Comparable<T>{
      public int compareTo(T o);
    }
    //Und die Implementierung
    public final class Integer extends Number implements Comparable<Integer>{
      public int compareTo( Integer anotherInteger ) { … }
    ...}


- Generic Methoden sind auch möglich
  - Dabei sucht der Compiler den kleinsten gemeinsamen Typen in der Typenhierarchie, (“Essen”, 1) haben z.B. Comparable als Gemeinsamen Basistypen
    public static <T, E> boolean isEqual(GenericsType<T> g1, GenericsType<E> g2){...}

Begriffe:

| **Begriff**                                                            | **Beispiel** |
| ---------------------------------------------------------------------- | ------------ |
| generischer Typ (engl. *generic type*)                                 | Pocket<T>    |
| Typvariable oder formaler Typparameter (engl. *formal type parameter*) | T            |
| parametrisierter Typ (engl. *parameterized type*)                      | Pocket<Long> |
| Typparameter (engl. *actual type parameter*)                           | Long         |
| Originaltyp (engl. *raw type*)                                         | Pocket       |



## Try-Catch

Bsp.

    Scanner reader = new Scanner(System.in);
    System.out.print("Write a number: ");
    
    try { //Wenn der Code richtig ausgeführt wird, wird der catch-Block übersprungen
      int num = Integer.parseInt(reader.nextLine());
      System.out.println("Looks good!");
    } catch (Exception e) { //
      System.out.println("You haven't written a proper number.");
    }



## Reguläre Ausdrücke
- Die matches-Methode von String kann für reguläre Ausdrücke benutzt werden
		
		if (string.matches("01[0-9]{7}")) {...} 
		//entspricht (0,1)*(0,...,9)^7

		"00|111|0000" //oder
		"trolo(lo)*"
		"trolo(lo)+" //"trolo(lo)(lo)*"
		"You have (deleted )?the name" //d.h. deleted kann weggelassen werden
		"1{2,}" //die "1" wird 2 bis n-mal wiederholt

		[145] //(1|4|5)
		[2-36-9] //(2|3|6|7|8|9)
		[a-c]* //(a,b,c)*


## Enum
    //Enum selbst
    public enum Season { winter, spring, summer, fall }
    //Verwendung
    public String getGermanName(Season season) { 
      switch (season) { 
        case Season.winter: return "Winter";  break; 
        case Season.spring: return "Frühling";  break; 
        case Season.summer: return "Sommer";  break; 
        case Season.fall  : return "Herbst";  break; 
      } 
    }


- Enum können auch Felder und Methoden haben
	    
		public enum Month { 
		january(31), 
		...
		december(31);

		private final int days;

		//Das Feld days muß initialisiert werden.
		//Deswegen der Konstruktor
		//Konstruktur ist private, weil wir nicht zusätzliche Monate einführen wollen

		private Month(int days) { 
			this.days = days; 
		}

		//Zugriffsmethode days() um Wert des days-Feldes zu bekommen
			public int days() { 
				return days; 
			} 
		}

		//Verwendung von days
		System.out.println(Month.january.days());


## Case
- The variable used in a switch statement can only be i**ntegers, convertable integers (byte, short, char), strings and enums**

Bsp.

    public static void main(String[] args) {
      
      int zahl = 2;
      
      switch (zahl) {
      case 1:
              System.out.println("Fall 1");
              break;
      case 2:
              System.out.println("Fall 2");
              break;
      case 3:
              System.out.println("Fall 3");
              break;
      default:
              System.out.println("Sonstiger Fall");
      }
      
    }


## Javadoc
- Die Kommentare zur Beschreibung von Klassen und Methoden werden von /** und */ eingklammert
- Es können HTML Befehle, sowie weitere Tags (siehe unten) benutzt werden
![](https://d2mxuefqeaa7sj.cloudfront.net/s_1B396AB1B03F5DEBF49EAAE06BBEDBDA06D0E84437C1B6C9FB13DE3EC3A0774F_1525257821601_image.png)



## Assertion
- Mit diesen werden innerhalb von Methoden Zusicherungen aufgestellt, um Vor- und Nachbedingungen sicherzustellen
- Wenn die Bedingung nicht erfüllt wird, so wird keine Exception sondern ein Error geworfen, dieser kann nicht gecatched werden, da es sich um ein Programmierfehler handelt
	
		//assert AssertConditionExpression : MessageExpression;
		assert x >= 0 && x < board.sizeX : "x-Wert ausserhalb des Spielbrettes";


## ToDo

Lernen

- Modules
- (Nested Classes)
## Fragen
- Warum kann nicht in foreach, bzw. während man iteriert nicht löschen



