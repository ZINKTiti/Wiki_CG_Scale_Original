### Arduino IDE installieren

Um die [Firmware](https://github.com/nightflyer88/CG_scale/releases) auf das ESP8266 Board zu laden, wird die [Arduino IDE](https://www.arduino.cc/en/main/software) benötig. Nachdem die Arduino IDE auf dem Computer installiert wurde, muss zuerst in den Einstellungen eine neu Boardverwalter-URL hinzugefügt werden.

![arduino_settings](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/arduino_settings.png)

Nun folgende Zeile einfügen:
_http://arduino.esp8266.com/stable/package_esp8266com_index.json_

![board_url](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/board_url.png)

Damit die Arduino IDE das ESP8266 Board kennt, muss dieses installiert werden. Dazu den **Boardverwalter** öffnen:

![board_manager](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/board_manager.png)

Jetzt nach **esp8266** suchen und installieren:

![esp8266_boardlib](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_boardlib.png)

Nun müssen noch ein paar Bibliotheken installiert werden. Dazu öffnet man den Bibliotheksverwalter.

**Sketch > Bibliotheken einbinden > Bibliotheken verwalten...**

![lib_manager](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/lib_manager.png)

Jetzt nach **HX711** suchen und die lib von Olav Kallhovd installieren:

![hx711](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/hx711_lib.png)

Danach nach **u8g2** suchen, und die lib von Oliver installieren:

![u8g2](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/u8g2_lib.png)

Zuletzt nach **json** suchen, und die lib von Benolt Blanchon installieren, es darf jedoch nur **Version 5.13.4** installiert werden !

![json_lib](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/json_lib.png)

Damit die Webpage auf das ESP8266 geladen werden kann, muss noch der [Filesystem uploader](https://github.com/esp8266/arduino-esp8266fs-plugin/releases) installiert werden. Nachdem die letzte Version als zip-Datei heruntergeladen und entpackt wurde, muss der Arduino Sketchbook Ordner auf dem Computer geöffnet werden. Dieser befindet sich normalerweise unter **Dokumente>Arduino** darin sollte sich bereits ein Ordner **libraries** und **tools** befinden. Ist der **tools** Ordner nicht vorhanden, so muss dieser erstellt werden. Danach den heruntergeladenen Ordner **ESP8266FS** in den **tools** kopieren.

![esp_tool](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp_tool.png)

Jetzt muss die Arduino IDE noch neu gestartet werden, und die IDE ist vorbereitet.

### Firmware laden

Die neuste [Firmware](https://github.com/nightflyer88/CG_scale/releases) herunterladen, zip-Ordner entpacken und den Ordner auf **CG_scale** umbenennen, sonst kommt anschliessend eine Fehlermeldung beim öffnen der Projektdatei. Nun die Arduino IDE starten und die Datei **CG_scale.ino** öffnen. Danach das ESP8266 Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. Flash Size auf **4M (1M SPIFFS)** einstellen.

![esp8266_board](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_board.png)

Jetzt kann oben links mit dem Pfeil die Firmware hochgeladen werden. Wurde der Uploadvorgang ohne Fehlermeldung abgeschlossen, hat man alles richtig gemacht.

![esp8266_upload](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_upload.png)

Zuletzt muss noch die Webpage hochgeladen werden. Dazu **Werkzeuge>ESP8266 Sketch Data Upload** wählen. Ist der Uplaod abgeschlossen, ist die CG scale fertig und betriebsbereit.

![esp8266_dataupload](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_dataupload.png)

### Firmware Update

Wird ein Update der Firmware gemacht, muss vor dem Update unbedingt ein Backup der Modelldatenbank erstellt werden. Dazu kann einfach auf der Webpage der CG scale im Modellmenü **Backup** gewählt werden, und es wird automatisch die Modelldatei _(models.json)_ heruntergeladen. Die Parameter bleiben erhalten und müssen nicht gesichert werden. 

Um die Firmware zu updaten, einfach in der Arduino IDE den Sketch und SPIFFS hochladen, so wie unter Punkt **Firmware laden**. Nach erfolgtem update, die _models.json_ im Modellmenü wiederherstellen. 

Ab Version V1.2 ist auch ein wireless Update per Wlan möglich. In der Arduino IDE unter **Port** wird dann ein Netzwerkport angezeigt, diesen wählen und die Firmware wie gewohnt hochladen. Wird vor dem Update nach einem Passwort gefragt, dann das Passwort des Wifi Access point eingeben. Treten Probleme mit dem wireless Update auf, dann zuerst einen Hardware Reset durchführen, gibt es weitere Probleme, dann das Passwort des Wifi Access point löschen.

![ota_port](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/img/esp8266_OTA_port.png)