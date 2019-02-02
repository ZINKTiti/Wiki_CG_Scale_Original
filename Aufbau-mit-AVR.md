### Firmware laden

Um die [Firmware](https://github.com/nightflyer88/CG_scale/archive/master.zip) auf das Arduino Board zu laden, wird die [Arduino IDE](https://www.arduino.cc/en/main/software) benötig. Nachdem die Arduino IDE auf dem Computer installiert wurde, müssen noch zwei Bibliotheken installiert werden. Unter Sketch > Bibliotheken einbinden > Bibliotheken verwalten... gelangt man in den Bibliotheksverwalter. Nun nach "HX711" suchen und die lib von Olav Kallhovd installieren:

![hx711](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/hx711_lib.png)

Danach nach "u8g2" suchen, und die lib von Oliver installieren:
![u8g2](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/u8g2_lib.png)

Nun das Arduino Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. Wenn die Datei "CG_scale.ino" in der Arduino IDE bereits geöffnet wurde, kann nun oben links (Pfeil) die Firmware hochgeladen werden. Wurde der Uploadvorgang ohne Fehlermeldung abgeschlossen, hat mans schon geschafft.

### Parameter Einstellungen

Die Parameter werden per serieller Schnittstellen parametriert. Das Arduino Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. Danach den Seriellen Monitor öffnen, unter Werkzeuge > Serieller Monitor. Es erscheint ein simples Text Menü. Man gibt die Menünummer ein (mit Enter bestätigen), und es erscheint der entsprechende Wert den man ändern möchte.

![menu](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/serial_menu.png)

Zuerst müssen die mechanischen Dimensionen definiert werden, also Menü 1-4. Die Batteriespannung wird in Menü 11 aktiviert. Alle Parameter werden im internen EEprom gespeichert und gehen auch nach einem Softwareupdate nicht verloren.