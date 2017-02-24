# Christkind Detektor 

Du wirst einen Detektor bauen der jede Bewegung registriert und einen Alarm auslößt. Dabei wirst du lernen wie du einen Bewegungssensor mit dem Raspberry Pi verbindest und wie du dein Scratch Programm darauf reagieren läßt. 

## Verbinde den Motion Sensor

Bevor du den Raspberry Pi hochfährst, verbinde den Sensor mit dem Raspberry Pi. 

Nehme drei female-to-female Jumper Kabel und verbinde sie mit den richtigen Pins deines Pis. 

Verbinde den mit `VCC` gelabelten Pin auf dem Sensor mit dem 5V Pin deines Raspberry Pis, verbinden den mittleren Pin mit  `OUT` gelabelten Pin mit dem GPIO Pin 4, und verbinde den mit `GND` gelabelten mit mit einem GND Pin auf deinem Pi. Hier siehst du noch einmal alles in dem Diagramm.

![](images/pir_wiring.png)

## Teste den Sensor

Weil wir die GPIO Pins nutzen, müssen wir den GPIO Server in Scratch starten.

- Starte Scratch
- Sobald Scratch läuft klicke auf `Start GPIO Server` aus dem `Edit` menu.
- du kannst Scratch auf Deutsch umstellen in dem du auf die Weltkugel klickst
- auf Deutsch kannst du den GPIO Server unter `Bearbeiten` starten
- alternativ kannst du auch einen Block mit Broadcast = gpioserveron in denen Code setzen

![scratch GPIO server](images/gpio-server.png)

Scratch benutzt den 'Fühlen' Block um zu überprüfen ob es einen Input auf den GPIO Pins gibt. Wenn ein Input registiert wird, verändert sich der Wert des Pins von `0` zu `1`. Da due deinen Bewegungssensor mit dem GPIO 4 Pins des Pis verbunden hats, müssen wir diesen Pin überprüfen. 

Als erstes müssen wir Scratch sagen das der Pin 4 input benutzt wird in dem wird das konfigurieren.

- Erstellen eine Boardcast/Sende Block:

![Sensor drop down](images/config-broadcast.png)

- Doppelklicke den Broadcast/Sende Block. Du musst das nur einmal machen. 

- In der  `Sensing`/`Fühlen`  Block Palette Klicke auf das Dropdown Feld des `Sensing`/`Fühlen`  Block und wähle `gpio4`.
- Setze den Hacken in der Check-Box auf der Linken Seite damit der Wert des Sensor auf der Bühne angezeigt wird.

**NOTE**: Wenn du`gpio4` nicht in der Liste siehts, stelle sicher, dass der  **GPIO server läuft** und dass du **deinen input konfiguriert hast**.


![Scratch sensing blocks](images/sensing-blocks.png)

Teste den Sensor indem du mit deiner Hand vor im winkst. Wenn der Sensor Bewegung registriert sollte sich der Wert auf der Bühne von `0` auf `1` ändern.

Wenn sich der Wert nicht verändert überprüfe, ob die Pins richtig verbunden sind.

## Male ein Sprite eines Christkinds oder Weihnachtsmanns

Klicke auf das 'Costumes'/'Kostüme' Tab und male einen Weihnachtsmann oder ein Christkind. Das wird angezeigt wenn der Bewegungssensor eine Bewegung registriert. 

Klicke auf den 'Sounds'/'Klang' Tab and importiere einen Klang aus dem 'Electronic' Ordner. 

## Programmiere was passiert wenn der Sensor eine Bewegung registriert

Jetzt haben wir einen Sensor der Bescheid gibt wenn er an oder aus ist. Wir können diesen Wert benutzn um den Fluss unseres Programmes zu steuern.  

Schreibe das folgende Script:

![Scratch script for santa detector](images/santa-script.png)

### Was macht das Programm?

Das `if` Statement checkt die ganze Zeit den Wert von Pin 4. Wenn der Wert sich auf `1` ändert passiert folgendes:

- zeige das Sprite
- mache das Sprite größer
- warte 0.25 Sekunden
- Spiele einen Sound
- mache den Sprite wieder normalgroß

Dieses Programm wird immer wieder ausgeführt solange der Sensorwert `1` also solange der Sensor eine Bewegung detektiert. 

Der `else` / `sonst` Block versteckt das Sprite lediglich wenn der Sensor Wert 0 ist. 

![santa sprite in Scratch](images/santa-stage.png)

## Baue den Detektor in deinem Zimmer auf!

- Am Heiligen Abend, baue deinen Pi auf mit dem Sensor auf die Balkon oder Terrassentür gerichtet. 
- Verbinden einen großen Lautsprecher mit deinem Pi
- Warte

**Disclaimer:** we cannot guarantee that this alarm will not scare Santa off so that you get no presents at all, not even a wrinkled satsuma in an old sock.

## Was als nächstes?

Andere Dinge die du ausprobieren kannst:

- schließe eine LED an 
- schließe einen Buzzer an
- Lasse den Hintergrund blinken 
- Animiere deine Sprites mit Kostümen
- Verändere den SOunf
- Nutze andere graphische Effekte als `Setze Größe`
- Lasse eine Message erscheinen 
- Baue einen Ständer für das PIR Modul
- schreib das Scratch Programm als Python programm
