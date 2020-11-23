# Einfach Zählen

## ~avatar avatar @unplugged
Weihnachtsplätzchen, Lichter an der Lichterkette, Kugeln oder Figuren am Weihnachtsbaum, weißt du eigentlich wie viel du davon hast? <br>
Um solche sachen einfach zu zählen ohne sich zu verzählen verwendet man oft einen sogenannten "Handzähler". <br>
Du kennst diesen kleinen Helfer vielleicht von Einlasskontrollen bei größeren Veranstaltungen.

## ~ @unplugged
Falls du sowas nicht zu hause hast, kein Problem. Dein Calliope mini kann das auch!!!


## Schritt 1
Um so einen Handzähler oder auch Klickzähler genannt zu programmieren nehmen wir erstmal aus dem Bereich ``||basic:Grundlagen ||`` den Block ``||basic: zeige Zahl||``. <br>
Dieser wird in den Block ``||basic:dauerhaft||`` geschoben. Im Simulator wird dir nun die Zahl angezeigt, welche im Block ``||basic: zeige Zahl||`` steht angezeigt. <br>
Jetzt möchtest du zum Zählen nicht immer eine neue Zahl in den Block einprogrammieren sondern das, was im Angezeigt werden soll mit den Knöpfen verändern können. Dazu mehr im nächsten Schritt.

```blocks
basic.forever(function () {
    basic.showNumber(0)
})
```

## Schritt 2 ~@unplugged
Um die angezeigte Zahl mit den Knöpfen A und B am Calliope verändern zu können dürfen wir sie nicht direkt in den Block ``||basic: zeige Zahl||`` programmieren, sondern müssen sie auf einer Variable speichern. <br>

Eine Variable kannst du dir vorstellen wie ein Behälter oder Gefäß. In den du verschiedene Dinge zum aufbewahren bzw. speichern hinein legen kannst. <br>
In unserem Fall wären dies Zahlen, Buchstaben, Wörter oder Listen.

## Schritt 3
Erstellen wir also eine Variable namens ``||Variables:Zähler||`` indem du auf den Bereich ``||Variables:Variablen||`` klickst. <br>
Nachdem erstellen erscheinen nun die Bläcke ``||Variables:setze auf ||`` und ``||Variables:ändere um ||``. <br>
Den Block ``||Variables:setze auf ||`` schieben wir in den Block ``||basic:beim Start||``. So wird der Variable beim Start des Calliope ein bestimmter Wert (in diesem Fall "0") zugewiesen. <br>
Um uns jetzt die gspeicherte Zahl wieder anzeigen zu lassen nehmen wir den Block ``||Variables:Zähler||`` und schieben ihn in den Block ``||basic: zeige Zahl||``. <br>

```blocks
let Zähler = 0


basic.forever(function () {
    basic.showNumber(Zähler)
})
```
## Schritt 4
Die Variable können wir ganz leicht mit einem Knopfdruck ändern indem wir den Block ``||input:wenn Knopf A gedrückt||`` aus dem Bereich ``||input:Eingaben||`` nehmen und uns hier den Block ``||Variables:ändere um 1 ||`` hineinschieben. <br>
Da in dem Block "ändere um 1" steht erhöht sich unsere Variable um eins bei jedem drücken des Knopfs.

```blocks
let Zähler = 0


basic.forever(function () {
    basic.showNumber(Zähler)
})

input.onButtonPressed(Button.A, function () {
    Zähler += 1
})

```
## Schritt 5
Um den Zähler auch wieder zurücksetzen zu können kann man beispielsweise die Tasten A und B gleichzeitig drücken, wenn hier in den Block ``||input:wenn Knopf A+B gedrückt||`` 
der Block ``||Variables:setze auf 0 ||`` geschoben wird.
```blocks
input.onButtonPressed(Button.A, function () {
    Zähler += 1
})
input.onButtonPressed(Button.AB, function () {
    Zähler = 0
})
let Zähler = 0

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


> Diese Seite bei [https://r00b1nh00d.github.io/klickzaehlertutorial/](https://r00b1nh00d.github.io/klickzaehlertutorial/) öffnen

## Als Erweiterung verwenden

Dieses Repository kann als **Erweiterung** in MakeCode hinzugefügt werden.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Neues Projekt**
* klicke auf **Erweiterungen** unter dem Zahnrad-Menü
* nach **https://github.com/r00b1nh00d/klickzaehlertutorial** suchen und importieren

## Dieses Projekt bearbeiten ![Build Status Abzeichen](https://github.com/r00b1nh00d/klickzaehlertutorial/workflows/MakeCode/badge.svg)

Um dieses Repository in MakeCode zu bearbeiten.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Importieren** und dann auf **Importiere URL**
* füge **https://github.com/r00b1nh00d/klickzaehlertutorial** ein und klicke auf Importieren

## Blockvorschau

Dieses Bild zeigt den Blockcode vom letzten Commit im Master an.
Die Aktualisierung dieses Bildes kann einige Minuten dauern.

![Eine gerenderte Ansicht der Blöcke](https://github.com/r00b1nh00d/klickzaehlertutorial/raw/master/.github/makecode/blocks.png)

#### Metadaten (verwendet für Suche, Rendering)

* for PXT/calliopemini
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
