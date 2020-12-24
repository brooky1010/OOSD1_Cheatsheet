# Samenvatting OOSD (sem 1)

## 1. Basis Java

### 1.1 Waarden afdrukken in de CUI

```Java
System.out.println("Welcome to Java programming");
```

> In `Strings` kan je speciale karakters gebruiken zoals:
>
> - `\n` newline = harde return
> - `\t` horizontale tab
> - `\r` carriage return
> - `\\` levert 1 backslash op
> - `\"` levert de dubbele quote op

```Java
System.out.printf("%d artikels over", aantal)
```

> In `Sysout.printf` kunnen we makkelijk variabelen in `Strings` toevoegen.
>
> - `%s` string
> - `%S` string in hoofdletters
> - `%d` integer
> - `%n` new line
> - `%f` float
> - `%15` lengte reserveren, in dit geval 15 characters
> - `%.2f` afronden op 2 getallen na de komma

### 1.2 Rekenkundige bewerkingen

In Java kunnen we op veel plekken rekenkundige bewerkingen gebruiken.

> - `*` vermenigvuldigen
> - `/` delen
> - `+`, `-` optellen en aftrekken
> - `%` restoperator

Bij het delen wordt alles achter de komma afgekapt. Men kan wel met de restoperator de rest berekenen. We kunnen ook haakjes gebruiken om prioriteiten te stellen.

## 2. Selectiestructuren

### 2.1 De `if` selectiestructuur

Het statement wordt alleen uitgevoerd als de voorwaarde WAAR is. Hiervoor hebben we enkele vergelijkingsoperatoren.

> - `==` exact gelijk
> - `!=` verschillend
> - `>`, `<` groter dan, kleiner dan
> - `>=` groter dan of gelijk aan
> - `<=` kleiner dan of gelijk aan

### 2.2 De `if else` selectiestructuur

Deze selectiestructuur is zeer gelijkaardig aan de gewone `if`-structuur, maar voert ook een stuk code uit wanneer de voorwaarde van de `if` structuur niet `true` is.

### 2.3 De conditionele operator

Wordt vaak gebruikt bij een `print` statement. Zo kan men compact een vergelijking schrijven.

- `statement`?`true`:`false`

```Java
System.out.printf("%s gelijk", a==b?"wel":"niet");
```

### 2.4 De `switch` meervoudige selectiestructuur

Met de `switch` structuur kunnen we makkelijk meervoudige selecties maken.

We vergelijken steeds de variabele tussen de haken met de labels bij iedere case. Als er niets voldoet, vallen we terug op `default`. Een `break` is daar optioneel, omdat het de laatste is en alle code uitvoert tot de closing bracket.

```Java
switch (variable) {
    case label1: statement1
                break;
    case label2: statement2
                break;
    case label3: statement3
                break;
    default: statement4
                (break;)
}
```

## 3. Herhalingsstructuren

### 3.1 De `while` herhalingsstructuur

Dit codeblock blijft uitgevoerd worden zolang de voorwaarde `true` is (ev. met teller).

```Java
while(voorwaarde) {
    //code
}
```

Een voorbeeld:

```Java
int teller = 0;
while (teller > 100) {
    System.out.printf("Waarde %d", teller);
    teller++;
}
```

### 3.2 De `for` lus

Een `for` lus is eigenlijk een compactere versie van de `while` herhalingsstructuur.

```Java
for(controlevariabele; voorwaarde; increment) {
    //code
}
```

Een voorbeeld:

```Java
for(int teller = 0; teller>=10; teller++) {
    //code
}
```

### 3.3 De `while` lus met schildwacht

Dit is eigenlijk exact hetzelfde als de gewone `while` lus, maar hier gebruiken we een schildwacht. De code zal dus blijven uitgevoerd worden tot men de waarde van de schildwacht ingeeft. Zie onderstaand voorbeeld:

```Java
while (punt != -1) {
    totaal = totaal + punt;
    puntenTeller = puntenTeller + 1;
    System.out.print("Geef score (/20) of -1 om te stoppen: ");
    punt = input.nextInt();
}
```

### 3.4 De `do while` lus

Deze lus lijkt op de `while` lus, met het grote verschil dat hij pas na het 1ste keer doorlopen van de code de voorwaarde controleert. Bij de gewone `while` lus controleert hij eerst de voorwaarde.

```Java
do {
    //code
}while(voorwaarde);
```

Een voorbeeld:

```Java
do {
    System.out.print("Geef een strikt positief geheel getal in: ")
    getal = input.nextInt();
} while (getal <=0);
```

### 3.4 **Samenvatting**

- Je gebruikt een `for` of een `while` indien je van tevoren weet om hoeveel herhalingen het gaat.
- Weet je niet van tevoren om hoeveel herhalingen het gaat, dan dien je een `while` of een `do-while` te gebruiken.
  - Je kiest voor een `while` indien de body van de while misschien nooit mag worden uitgevoerd.
  - Je kiest voor een `do-while` indien de body van de `do-while` tenminste één keer moet worden uitgevoerd.

## 4. Samengestelde toekennings-, increment- en decrementoperatoren

### 4.1 Samengestelde toekenningsoperatoren

In Java kunnen we in bepaalde situaties uitdrukkingen voor toekenningen afkorten.

```Java
x = x operator a
wordt
x operator= a;
```

Voorbeeld:

```Java
x -= a; // x = x - a
x *= a; // x = x * a
```

### 4.2 Increment- en decrementoperatoren

In het bijzonder komt het vaak voor, dat een telvariabele met 1 moet verhoogd of verlaagd worden.

Dus in de plaats van:

```Java
teller += 1;
teller -= 1;
```

Gebruiken we:

```Java
teller++; //of ++teller;
teller--; //of --teller;
```

Wat is nu het verschil tussen `++teller` en `teller++`?

Bijvoorbeeld: Bij `resul1 = teller++;` wordt eerst de waarde van `teller` aan `result1` toegewezen, daarna pas verhoogt met 1. Bij `resul1 = ++teller;` zal eerst `teller` met 1 verhoogt worden en daarna pas toegwezen worden aan `resul1`.

## 5. Logische operatoren

```Java
&& //conditionele EN
& //logische EN
|| //conditionele OF
| //logische inclusieve OF
^ //logische exclusieve OF (XOR, dus maar 1 van de 2 true)
! //logische NOT
```

> De logische operatoren `&` en `|` evalueren steeds **BEIDE** operanden!
>
> Dit wil zeggen: bij conditionele OF stopt hij al met vergelijken als de eerste waarde WAAR is. Bij conditionele EN stopt hij als de eerste waarde al ONWAAR is.

## 6. De statements `break` en `continue`

- `break`/`continue`: veranderen de stroom van de controle
- `break` statement
  - veroorzaakt een onmiddelijke exit uit de controlestructuur
  - wordt gebruikt in `while`, `for`, `do-while` en `switch` statements
- `continue` statement
  - slaat de resterende statements in de body van de controlestructuur over
  - gaat verder naar de volgende iteratie
  - wordt gebruikt in `while`, `for` en `do-while` statements

## 7. Primitieve datatypes

Primitieve datatypes zijn "bouwblokken" voor ingewikkeldere types (zoals `String`).

### 7.1 Primitieve datatype `boolean`

Variabelen van het type `boolean` kunnen slechts twee waarden bevatten: `true` of `false`.

### 7.2 Primitieve datatype `char`

In variabelen van het type `char` kan je **één** letter of **één** ander teken opslaan. Nooit meer dan één.
Zo'n teken moet je in het programma tussen apostrofs zetten, bijvoorbeeld de letter **a** als `'a'`.

> De reden dat je apostrofs moet gebruiken, is om aan de compiler duidelijk te maken dat dit een `char` is een geen variabele.

### 7.3 Primitieve datatype `byte`

In een variabele van het type `byte` kun je gehele getallen van -128 t.e.m. 127 bewaren.

> Als we 1 optellen bij 127 komen we terecht bij -128.

### 7.4 Primitieve datatype `short`

In een variabele van het type `short` kun je gehele getallen van **-32768** t.e.m. **32767** bewaren.

### 7.5 Primitieve datatype `int`

In een variabele van het type `int` kun je gehele getallen van **-2 147 483 648** tot **2 147 483 647** bewaren.

### 7.6 Primitieve datatype `long`

In een variabele van het type `long` kun je gehele getallen van **–9 223 372 036 854 775 808** tot **9 223 372 036 854 775 807** bewaren.

### 7.7 Primitieve datatypen: `float` en `double`

In veel gevallen heb je reële getallen nodig, zoals bv. 24.65. Dit zijn **floating-point** getallen. Hier gebruiken we `float` en `double` voor.

- `float`
  - storing single-precision floating-point
  - nauwkeurigheid van 6 tot 7 cijfers
- `double`
  - storing double-precision floating-point
  - nauwheurigheid van 15 cijfers

## 8. Klasse en object

### 8.1 Object

Software objecten zijn een weerspiegeling van real-world objecten: ze kunnen **onderscheiden** worden, ze hebben **eigenschappen** en ze hebben **gedrag**.

#### 8.1.1 **Kenmerken van een object**

Elk object heeft een **toestand**, een **gedrag** en een **identiteit**.

- **Toestand** <br/>
  Objecten hebben bepaalde eigenschappen (bv. kleur, hoogte, breedte,...) dit bepaalt zijn toestand. We noteren deze eigenschappen op een meer gestructureerde manier. - Eigenschappen worden voorgesteld door een **attribuut**.
  - Elk attribuut heeft een **naam** en een **type**. (bv. `int test`)
- **Gedrag**
  - Objecten vragen aan andere objecten om iets te doen
  - Zo doen objecten beroep op de dienst van andere objecten
  - De manier van oproepen verschilt van objecttype tot objecttype.
- **Identiteit** <br/>
  Ieder object heeft een unieke identeit. Zelfs als gebruiken ze dezelfde klasse. Dit maakt het mogelijk ze onderling te onderscheiden.

#### 8.1.2 **Verantwoordelijkheid van een object**

Een object heeft een duidelijke, wel afgebakende verantwoordelijkheid. Deze wordt gerealiseerd via:

- de toestand, de eigenschappen van het object
- het gedragen, de diensten die het object aanbiedt

Software heeft een duidelijke, wel afgebakende verantwoordelijkheid, het biedt een wel gedefineerde functionaliteit aan, deze wordt gerealiseerd via

- de create van objecten
- een complexe interactie tussen objecten

#### 8.1.3 **Relaties tussen objecten**

Tussen objecten bestaan relaties. Deze ontstaan wanneer één of meerdere attributen van een object, verwijzen naar een ander object. Dit is mogelijk door in een klasse eigenschappen op te nemen die als type een andere klasse hebben.

### 8.2 Abstractie

Abstractie verwijst naar het enkel opnemen van de noodzakelijke eigenschappen en/of gedrag en tegelijk het verbergen van irrelevante details. Zo reduceren we de complexiteit van een applicatie en bevorderen we de efficiëntie ervan.

### 8.3 Klasse

Een klasse bevat de omschrijving van de eigenschappen en het gedrag van soortgelijke objecten.

## 9. Voorstelling klasse in UML

**UML**: Unified Modeling Language: Dit is een **modelleertaal** die toelaat OO analyses en ontwerpen te maken. Het is een grafische weergave van kenmerken van een OO systeem. Wij gebruiken Visual Paradigm.
