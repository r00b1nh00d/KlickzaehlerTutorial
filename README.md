# Einfach Zählen

## ~avatar avatar @unplugged
Weihnachtsplätzchen, Lichter an der Lichterkette, Kugeln oder Figuren am Weihnachtsbaum: <br>
weißt du eigentlich, wie viel du davon hast? <br>
Um solche Sachen einfach zu zählen, ohne sich zu verzählen, verwendet man oft einen sogenannten ["Handzähler"](https://www.google.com/search?q=handz%C3%A4hler&rlz=1C1CHBD_deDE928DE928&oq=handz%C3%A4hler&aqs=chrome..69i57j0l5j69i60j69i61.3920j1j7&sourceid=chrome&ie=UTF-8). <br>
Du kennst diesen kleinen Helfer vielleicht von Einlasskontrollen bei größeren Veranstaltungen.

## ~ @unplugged
Falls du sowas nicht zuhause hast, kein Problem. Dein Calliope mini kann das auch!!!
![Zaehler](https://github.com/r00b1nh00d/KlickzaehlerTutorial/blob/master/Zaehler.gif?raw=true)


## Schritt 1
Um so einen Handzähler oder auch Klickzähler genannt zu programmieren, nehmen wir erstmal aus dem Bereich ``||basic:Grundlagen ||`` den Block ``||basic: zeige Zahl||``. <br>
Dieser wird in den Block ``||basic:dauerhaft||`` geschoben. Im Simulator wird dir nun die Zahl angezeigt, welche im Block ``||basic: zeige Zahl||`` steht. <br>
Jetzt möchtest du zum Zählen nicht immer eine neue Zahl in den Block einprogrammieren, sondern die Zahl mit den Knöpfen verändern können. Dazu erfährst du mehr im nächsten Schritt.

```blocks
basic.forever(function () {
    basic.showNumber(0)
})
```

## Schritt 2 ~@unplugged
Um die angezeigte Zahl mit den Knöpfen A und B am Calliope verändern zu können, dürfen wir sie nicht direkt in den Block ``||basic: zeige Zahl||`` programmieren, sondern müssen sie auf einer Variable speichern. <br>

Eine Variable kannst du dir vorstellen wie ein Behälter oder Gefäß, in den du verschiedene Dinge zum Aufbewahren bzw. Speichern hineinlegen kannst. <br>
In unserem Fall wären dies Zahlen, Buchstaben, Wörter oder Listen.

## Schritt 3
Erstellen wir also eine Variable namens ``||Variables:Zähler||``, indem du auf den Bereich ``||Variables:Variablen||`` klickst. <br>
Nach dem Erstellen erscheinen nun die Blöcke ``||Variables:setze auf ||`` und ``||Variables:ändere um ||``. <br>
Den Block ``||Variables:setze auf ||`` schieben wir in den Block ``||basic:beim Start||``. So wird der Variable beim Start des Calliope ein bestimmter Wert (in diesem Fall "0") zugewiesen. <br>
Um uns jetzt die gespeicherte Zahl wieder anzeigen zu lassen, nehmen wir den Block ``||Variables:Zähler||`` und schieben ihn in den Block ``||basic: zeige Zahl||``. <br>

```blocks
let Zähler = 0
Zähler = 0

basic.forever(function () {
    basic.showNumber(Zähler)
})
```
## Schritt 4
Die Variable können wir ganz leicht mit einem Knopfdruck ändern, indem wir den Block ``||input:wenn Knopf A gedrückt||`` aus dem Bereich ``||input:Eingaben||`` nehmen und uns hier den Block ``||Variables:ändere um 1 ||`` hineinschieben. <br>
Da in dem Block "ändere um 1" steht, erhöht sich unsere Variable um eins bei jedem Drücken des Knopfes.

```blocks
let Zähler = 0
Zähler = 0

basic.forever(function () {
    basic.showNumber(Zähler)
})

input.onButtonPressed(Button.A, function () {
    Zähler += 1
})

```
## Schritt 5
Um den Zähler auch wieder zurücksetzen zu können, kann man beispielsweise die Tasten A und B gleichzeitig drücken, wenn hier in den Block ``||input:wenn Knopf A+B gedrückt||`` 
der Block ``||Variables:setze auf 0 ||`` geschoben wird.
```blocks
input.onButtonPressed(Button.A, function () {
    Zähler += 1
})
input.onButtonPressed(Button.AB, function () {
    Zähler = 0
})
let Zähler = 0
Zähler = 0
basic.forever(function () {
    basic.showNumber(Zähler)
    basic.pause(250)
    basic.showLeds(`
        . . . . .
        . . . . .
        . # # # .
        . . . . .
        . . . . .
        `)
})
```

## ~ @unplugged
Ganz ähnlich zum Klickzähler kannst du dir auch ein Schild Programmieren, welches "nicht stören" oder "Open" bzw. "Close" anzeigt. <br>
Ein Video dazu findest du auch hier: [Open/Close-Schild](https://www.youtube.com/watch?v=Jlv2vZMC6w8)
