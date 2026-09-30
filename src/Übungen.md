### Übung 1: IF-Statement
Schreibe ein [If-Statement](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/if...else), welches einen Variablenwert auf seinen Datentypen prüft.
1. Deklariere eine Variable und weise ihr einen Wert zu (z.B. Nummer oder Zeichenkette)
2. Schreibe die If-Anweisung mit mehreren else-if-Zweigen - du möchstest auf "number", "string", "boolean" und "null" prüfen.
3. In den Konditionen (d.h. in den runden Klammern) verwendest du `typeof`, deinen Variablennamen sowie den strikten Gleichheitsoperator `===`um gegen jeweils eine der vier Zeichenketten in 2. zu prüfen (also z.B. gegen "number").
4. Im jeweiligen Anwendungsblock (d.h. in den geschwungenen Klammern) schreibst du ein `console.log()` welches eine Nachricht über den gefundenen Datentyp enthält.
5. Öffne die Browser-Konsole und ändere die Datentypen die du deiner Variablen (in 1.) zuweist, um die verschiedenen Zweige zu testen. Stimmt das alles?


Reminder:
```
// If-Syntax

 const userName = "Tim";  // Hier weisen wir eine Zeichenkette zu.

  if (userName === "Tim") {
    console.log("Access denied");
  } else if (userName === "Anna") {
    console.log("Access granted");
  } else {
    console.log("Unknown user");
  }

```

---

### Übung 2: Ternärer Operator / Ternary Operator
Im HTML Teil der App.js können wir Werte aus dem JavaScript Teil nutzen - z.B. Variablen. Diese müssen in {} geschrieben werden.
Beispiel:
```
export default function App() {

const userRole = "Admin";

return (
  <p>User is {userRole} </p>
)

}

```

Ausdrücke (Expressions) werden  zu Werten evaluiert und können daher ebenfalls im HTML Teil benutzt werden. Der ternäre Operator gibt einen (von zwei möglichen) Werten zurück - daher können wir diesen auch im HTML-Teil nutzen!

Führe nun folgende Schritte aus:

- Definiere im JS-Teil eine Variable "isTheTruth" und gibt ihr einen boolschen Wert.
- Schreibe im HTML Teil (innerhalb von `return()`) ein `p`-Element und einen beliebigen Satz. Achtung: Es muss immer ein (1) äusseres Element geben - wenn du einen Fehler bekommst dann hast du vielleicht mehrere Elemente auf der gleichen Hierarchiestufe.
- Gib dem p-Element einen Inline-Stil mit `style={{color: "blue"}}` - der Text sollte nun blau angezeigt werden.
- Ersetze "blue" mit diesem Ausdruck / ternären Operator: `isTheTruth ? "green" : "red"`.
- Ändere den boolschen Wert und überprüfe das Ergebnis - die Farbe sollte sich jeweils anpassen.

Die Übung sollte dir zeigen:
- Das Inline-Stile ihren Zweck haben können - sie können genutzt werden um dynamisch auf Werte und Wertänderungen zu reagieren.
- Der Ternäre Operator im HTML Teil genutzt werden kann, weil er einen Wert zurück gibt (er ist ein Ausdruck / Expression - im Gegensatz zu den IF/Switch-Statements).
- Die Verknüpfung von HTML und JS (in React) sehr praktisch ist.
Statt der Farbe hätten wir auch z.B. den Text-Inhalt des `<p>`-Elements dynamisch ändern können.

---

### Übung 3: Funktionen A - Funktionsdeklaration

Schreibe in der App.js (Funktionsblock) eine Funktion "multiply". Die Funktion soll zwei Parameter erhalten können, wovon der zweite Parameter einen "default"-Wert von 2 haben soll. Die Funktion soll:
- Zunächst prüfen ob beide Parameter vom Typ "number" sind. Dazu brauchst du ein `if()-Statement`, `typeof`,  den Ungleichheitsoperator `!==` sowie den logischen OR-Operator (`||`). 
- Wenn einer oder beide der Parameter keine Zahl ist, soll die Funktion eine (beliebige) Fehlermeldung in die Konsole drucken (console.log()).
- Falls beide Parameter Zahlen sind, sollen beide Zahlen multipliziert werden und das Produkt in die Konsole gedruckt werden.
- Vergiss den Funktionsaufruf nicht und teste deine Funktion mit einem (1) und zwei Argumenten.

Reminder:

```
function funktionsName (parameter, parameter=defaultWert){
  // Funktionsblock mit Logik

  return;  // console.log() ist ein "Nebeneffekt", wir geben in dieser Aufgabe keinen Wert zurück

}

funktionsName(argument/e)  // Funktionsaufruf, 1-2 Argumente

```

---


### Übung 4: Funktionen B - Pfeilfunktionen / "Arrow functions"

Schreibe alle Funktionen als Arrow-Functions! Sie sollen immer einen Wert zurückgeben. Nutze `console.log(deinFunktionsAufruf(Argumente))` um die Ergebnisse zu überprüfen. Du brauchst keine Datentypen o.ä. überprüfen.

#### 4.1 Leerzeichen einfügen
Schreibe eine Funktion, welche zwei Strings als Parameter erhält und diese mit einem Leerzeichen getrennt zurückgibt. Du brauchst dafür einen [Template-String](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Template_literals), in welchem du beide Parameter und das Leerzeichen verwendest. 

Reminder: 
```
const wordOne = "Hallo"
const wordTwo = "Welt"

`Eine Begrüssung mit fünf Buchstaben: ${wordOne}`  // Dieser Template String verwendet nur eine (1) Variable.
```

#### 4.2 Zahlen vergleich
Schreibe eine Funktion die prüft, ob eine Zahl kleiner, grösser oder gleich 0 ist und einen entsprechenden String zurückgibt. Dafür brauchst du ein If-Statement. In den verschiedenen Zweigen (if, else if, else) benutzt du jeweils ein  `return`-Statement, da ein Wert zurückgegeben werden soll (kein console.log() als "Nebeneffekt").

#### 4.3 Max
Schreibe eine Funktion welche den grösseren von zwei Zahlenwerten zurückgibt. Hier kannst du z.B. den [Ternären Operator](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/Conditional_operator) benutzen.

---


### Übung 5: Array-Methoden
Für die Übung genügt es, den Code im Funktionsblock der App.js zu schreiben und dir den Array per console.log ausgeben zu lassen (`console.log(meinArray)`). Es müssen also keine HTML erzeugt werden.

Definiere zunächst einen Array, der mehrere Zahlen enthält.

#### 5.1 map()
Iteriere mit `.map()` über den Array und multpliziere jedes Element mit der Zahl 3. `map()` verändert deinen Ausgangsarray nicht, daher musst du das Ergebnis einer neuen Variablen zuweisen. Diese kannst du dir dann mit `console.log()` anzeigen lassen.

Was müsstest du ändern, damit jedes Element mit seinem Index, anstatt mit der Zahl 3 multipliziert wird? Probiere es aus und verände den Code entsprechend. 

Reminder:
```
const userList = ["Tim", "Anna", "Admin"]
userList.map( (user, index) => user)

// oder auch
userList.map( (user, index) => { 
  // ganz viel Code
  return user;
})

```

#### 5.2 filter()
Führe die folgenden Schritte aus:
- Definiere einen Array mit fünf beliebigen Nutzernamen (Strings). 
- Filter den Array mit `.filter()` und weise das Ergebnis einer neuen Variablen zu (`filter()` modifiziert den Ursprungsarray nicht). 
- Innerhalb der runden Klammern wird eine Funktion erwartet - schreibe dort diese Arrow-Function: `username => username.includes("a")`.
- Log den neuen Array mit `console.log()` - stimmt das Ergebnis?

Erklärung:
- includes() ist eine Methode auf einem String (dem jeweiligen Nutzernamen über den die Filter-Methode iteriert). Sie gibt true / false zurück.
- Zeichenketten / Strings lassen sich als ein Array von einzelnen Zeichen begreifen. Viele Array-Methoden können auch für Strings genutzt werden (siehe die JS-Referenz zu String und Array Methoden)
- Wir könnten `include()` auch mit einem ternären Operator in einer `map()`Funktion kombinieren, z.B. um alle Nutzer:innen mit "a" im Namen anders zu prozessieren, als die restlichen Nutzer:

`userList.map(username => username.includes("admin") ? grantAdminRights() : grantUserRights())`


---

## Weiterführende Aufgaben:

### Übung 6: IF-Statement zu Switch-Statement

Schreibe das IF-Statement aus Aufgabe 1 in ein [Switch-Statement](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/switch) um. Du siehst ein Beispiel für die Syntax unten. 

Erklärung / Hinweis:
Jeder "case" entspricht einem "if"-Zweig, wobei "default" ein generelles "else" ist, fall kein case  zutrifft. In jedem "case" können mehrere Anweisungen ("statements") stehen. "Break" ist speziell, es stoppt die Evaluation weiterer, nachfolgender "cases" ("fallthrough")- das ist für die meisten Anwendungsfälle gewünscht.

```
// Schreib mich um!

 const someVariableType = 42; // Alternativen: "einString", true, null

  if (typeof someVariableType === "number") {
    console.log("number detected!");
  } else if (typeof someVariableType === "string") {
    console.log("string detected!");
  } else if (typeof someVariableType === "boolean") {
    console.log("boolean detected!");
  } else if (typeof someVariableType === "null") {
    console.log("null detected!"); // Wirklich? Oder nicht?
  } else {
    console.log("unknown type detected");
  }

```

Reminder:
```
// Switch Syntax:

const userType = "a role"

switch (userType) {     // in () auch Expressions möglich
  case "admin":
    console.log("Welcome admin!");
    break;      // Nicht vergessen - sonst "fallthrough"
  case "user":
    console.log("Welcome user!"); 
    break; // Nicht vergessen - sonst "fallthrough"
default:
    console.log("Welcome unknown!"); 
}

```