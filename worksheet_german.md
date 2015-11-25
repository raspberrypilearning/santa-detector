# Christkind Detektor 

Du wirst einen Detektor bauen der jede Bewegung detektiert und einen Alarm auslößt. Dabei wirst du lernen wie du einen Bewegungssensor mit dem Raspberry Pi verbindest und wie du dein Scratch Programm darauf reagieren läßt. 

## Verbinde den Motion Sensor

Bevor du den Raspberry Pi hochfährst, verbinden den Sensor mit dem Raspberry Pi. 

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

Scratch benutzt den 'Fühlen' Block to check if there is any input on the GPIO pins. If there is an input, the value of the pin changes from `0` to `1`. As you connected the PIR sensor to GPIO pin 4 of the Pi, we need to monitor that. 

Firstly we need to tell Scratch that pin 4 will be used as an input by *config*uring it. 

- Erstellen eine Boardcast/Sende Block:

![Sensor drop down](images/config-broadcast.png)

- Doppelklicke den Broadcast/Sende Blck. Du musst das nur einmal machen. 

- In der  `Sensing`/`Fühlen`  Block Palette Klicke auf das Dropdown Feld des `Sensing`/`Fühlen`  Block und wähle `gpio4`.
- Setze den Hacken in der Check-Box auf der Linken Seite damit der Wert des Sensor auf der Bühne angezeigt wird.

**NOTE**: Wenn du`gpio4` nicht in der Liste siehts, stelle sicher ob der  **GPIO server is running** and that you have **run the config broadcast**.


![Scratch sensing blocks](images/sensing-blocks.png)

Test the PIR sensor by waving your hand in front of it. When it detects movement, the value on the screen should change from `0` to `1`.

If the value doesn't change, check that the correct pins are connected.

## Draw a sprite and add sound

Click on the 'Costumes' tab and draw a Santa sprite. This will be displayed when the PIR senses movement.

Click on the 'Sounds' tab and import a sound from the 'Electronic' folder. I've used a siren called 'Whoop' here.

## Program what happens when the detector spots movement

Now we have a sensor that reports when it is on or off, we can use this value to control the flow of our program.  

Schreibe das folgende Script:

![Scratch script for santa detector](images/santa-script.png)

### Was macht das Programm?

Das `if` Statement checket die ganze zeit den Wert von Pin 4. Wenn der Wert sich auf `1` ändert passiert folgendes:

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

- Lasse den Hintergrund blinken 
- Animiere deine Sprites mit Kostümen
- Verändere den SOunf
- Nutze andere graphische Effekte als `Setze Größe`
- Lasse eine Message erscheinen 
- Baue einen Ständer für das PIR Modul
