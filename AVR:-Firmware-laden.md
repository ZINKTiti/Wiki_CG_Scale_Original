### Arduino IDE installieren

Um die [Firmware](https://github.com/nightflyer88/CG_scale/releases) auf das Arduino Board zu laden, wird die [Arduino IDE](https://www.arduino.cc/en/main/software) benötig. Nachdem die Arduino IDE auf dem Computer installiert wurde, müssen noch zwei Bibliotheken installiert werden. Dazu öffnet man den Bibliotheksverwalter.

**Sketch > Bibliotheken einbinden > Bibliotheken verwalten...**

![lib_manager](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/lib_manager.png)

Nun nach **HX711** suchen und die lib von Olav Kallhovd installieren:

![hx711](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/hx711_lib.png)

Danach nach **u8g2** suchen, und die lib von Oliver installieren:
![u8g2](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/u8g2_lib.png)

### Firmware laden

Die neuste [Firmware](https://github.com/nightflyer88/CG_scale/releases) herunterladen, zip-Ordner entpacken und den Ordner auf **CG_scale** umbenennen, sonst kommt anschliessend eine Fehlermeldung beim öffnen der Projektdatei. Nun die Arduino IDE starten und die Datei **CG_scale.ino** öffnen. Danach das Arduino Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. 

![arduino_board](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/arduino_board.png)

Jetzt kann oben links mit dem Pfeil die Firmware hochgeladen werden. Wurde der Uploadvorgang ohne Fehlermeldung abgeschlossen, hat man alles richtig gemacht, und die CG scale funktioniert.

![arduino_upload](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/arduino_upload.png)

### Firmware Update

Vor dem Update müssen die Parameter nicht gesichert werden, diese sind im internen Eeprom gespeichert und bleiben erhalten. Um die Firmware zu updaten, einfach in der Arduino IDE den Sketch hochladen, so wie unter Punkt **Firmware laden**.