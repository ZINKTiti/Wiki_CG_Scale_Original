### Elektrischer und mechanischer Aufbau

Je nach gewünschtem Messbereich können die Wiegezellen nach belieben dimensioniert werden, solche gibt es von 1-200Kg. Die Zellen dürfen unterschiedlich gross sein. Die Messwandler der Wiegezellen müssen einen HX711 Chip enthalten. Als CPU wird ein Node MCU V1.0 mit ESP8266 Chip empfohlen.

#### Materialliste:

- 1x [OLED Display 1.3" 4Pin I2C White](https://www.aliexpress.com/item/1-3-Inch-OLED-Module-White-Color-128X64-OLED-LCD-LED-Display-Module-1-3-IIC/32844104782.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0) (optional)
- 1x [NodeMcu ESP8266 CP2102](https://www.aliexpress.com/item/New-Wireless-module-NodeMcu-Lua-WIFI-Internet-of-Things-development-board-based-ESP8266-with-pcb-Antenna/1967836272.html?spm=2114.search0104.3.280.484563a8cswkJr&ws_ab_test=searchweb0_0,searchweb201602_3_10065_10068_319_10059_10884_317_10887_10696_321_322_10084_453_10083_454_10103_10618_10307_537_536_10902_10134,searchweb201603_57,ppcSwitch_0&algo_expid=8ffca336-38fc-429c-9530-e23d73a407b9-37&algo_pvid=8ffca336-38fc-429c-9530-e23d73a407b9&transAbTest=ae803_3)
- 3x [Loadcell + HX711 AD Module](https://www.aliexpress.com/item/1kg-2kg-3kg-5kg-10kg-20kg-Weighing-Sensor-Load-Cell-Weight-Sensor-Electronic-Kitchen-Scale-HX711/32863297220.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0)
- 1x [Metall Film Resistor 10k 1%](https://www.aliexpress.com/item/100pcs-1-4W-1R-22M-1-Metal-film-resistor-100R-220R-1K-1-5K-2-2K/32847096736.html?spm=2114.search0604.3.1.1ff530c2WP491F&s=p&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=5b45da6d-ef50-42bf-9243-883fe4708342-0&algo_pvid=5b45da6d-ef50-42bf-9243-883fe4708342) (optional)
- 1x [Metall Film Resistor 20k 1%](https://www.aliexpress.com/item/100pcs-1-4W-1R-22M-1-Metal-film-resistor-100R-220R-1K-1-5K-2-2K/32847096736.html?spm=2114.search0604.3.1.1ff530c2WP491F&s=p&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=5b45da6d-ef50-42bf-9243-883fe4708342-0&algo_pvid=5b45da6d-ef50-42bf-9243-883fe4708342) (optional)


#### Elektroschema:
![schema](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_schema_ESP8266.png)

Werden nur zwei Wiegezellen benötigt, so wird Zelle nr. 3 weggelassen. Wird die Spannungsmessung nicht benötig, können die beiden Wiederstände R1 und R2 weggelassen werden. Werden andere Wiederstände verwendet, müssen die Werte in den Einstellungen angepasst werden.

#### Mechanische Anordnung:
![mechanic](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_mechanics.png)

Die Wiegezellen 1 + 3 dürfen auch vor dem Anschlag sein, der Wert X1 wird dann negativ eingegeben.

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

Jetzt muss die Arduino IDE noch neu gestartet werden, und die IDE ist vorbereitet.

### Firmware laden

Die neuste [Firmware](https://github.com/nightflyer88/CG_scale/releases) herunterladen, zip-Ordner entpacken und den Ordner auf **CG_scale** umbenennen, sonst kommt anschliessend eine Fehlermeldung beim öffnen der Projektdatei. Nun die Arduino IDE starten und die Datei **CG_scale.ino** öffnen. Danach das ESP8266 Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. Flash Size auf **4M (1M SPIFFS)** einstellen.

![esp8266_board](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_board.png)

Jetzt kann oben links mit dem Pfeil die Firmware hochgeladen werden. Wurde der Uploadvorgang ohne Fehlermeldung abgeschlossen, hat man alles richtig gemacht.

![esp8266_upload](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_upload.png)

Zuletzt muss noch die Webpage hochgeladen werden. Dazu **Werkzeuge>ESP8266 Sketch Data Upload** wählen. Ist der Uplaod abgeschlossen, ist die CG scale fertig und betriebsbereit.

![esp8266_dataupload](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/esp8266_dataupload.png)

### Betrieb und Einstellungen

Beim ersten start der CG scale wird ein Hotspot **CG scale** generiert. Mit dem Computer/Handy verbindet man sich mit diesem Wlan, danach öffnet man den Webbrowser und gibt die IP-Adresse **1.2.3.4** ein. Man gelangt auf die Webpage der CG scale. 

![cgscale_home](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/cgscale_home.png)

Oben rechts gelangt man mit dem Button **settings** in die Einstellungen. Zuoberst finden man die WiFi Einstellungen. Man kann hier sein Home Wlan wählen, damit sich die CG scale automatisch in das eigene Netzwerk einloggt. Darunter kann man den Access Point (Hotspot) einstellen. Wird die CG scale z.B. auf dem Feld verwendet und das eigene Wlan ist ausser Reichweite, wird der hier definierte Hotspot erstellt.

![cgscale_wifisettings](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/cgscale_wifisettings.png)

Anschliessend können die Parameter eingestellt werden, alternativ können diese auch per serieller Schnittstellen eingestellt werden. Zuletzt müssen die Einstellungen gespeichert werden. 

Die Parameter X1, X2 und X3 werden Modellspezifisch gespeichert, dies ist bei mechanisch verstellbaren Schwerpunktwaagen sehr hilfreich.

![cgscale_settings](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/cgscale_settings.png)


### Kalibrierung

Zur Kalibrierung gibt es zwei Möglichkeiten:

#### 1. Manuell

Man kalibriert anhand eines Referenzgewichts jede einzelne Wiegezelle. Das Gewicht auf eine Wiegezelle legen und den entsprechenden Kalibrierfaktor anpassen bis der angezeigte Wert mit dem Referenzgewicht übereinstimmt. Alternativ kann der Kalibrierfaktor mit folgender Formel berechnet werden:

_Kalibrierfaktor = KalFaktorAlt / (RefGewicht / IstGewicht)_

#### 2. Automatisch

Anhand eines Referenzobjekts. Zum Beispiel ein Modell, von dem das genaue Gewicht und der genaue Schwerpunkt bekannt ist. Alternativ kann auch ein Brett mit einem Gewicht verwendet werden. Das Brett sollte symmetrisch sein und das Gewicht mittig auf dem Brett positioniert sein. Ist das Gewicht und der Schwerpunkt von unserem Referenzobjekt bekannt, müssen diese Parameter in den Einstellungen eingegeben werden. Nun das Referenzobjekt auf die Waage legen, und in den Einstellungen den Kalibriervorgang starten. 

### Firmware Update

Wird ein Update der Firmware gemacht, muss vor dem Update unbedingt ein Backup der Modelldatenbank erstellt werden. Dazu kann einfach auf der Webpage der CG scale im Modellmenü **Backup** gewählt werden, und es wird automatisch die Modelldatei _(models.json)_ heruntergeladen. Die Parameter bleiben erhalten und müssen nicht gesichert werden. 

Um die Firmware zu updaten, einfach in der Arduino IDE den Sketch und SPIFFS hochladen, so wie unter Punkt **Firmware laden**. Nach erfolgtem update, die _models.json_ im Modellmenü wiederherstellen. 

Ab Version V1.2 ist auch ein wireless Update per Wlan möglich. In der Arduino IDE unter **Port** wird dann ein Netzwerkport angezeigt, diesen wählen und die Firmware wie gewohnt hochladen. Wird vor dem Update nach einem Passwort gefragt, dann das Passwort des Wifi Access point eingeben. Treten Probleme mit dem wireless Update auf, dann zuerst einen Hardware Reset durchführen, gibt es weitere Probleme, dann das Passwort des Wifi Access point löschen.

![ota_port](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/img/esp8266_OTA_port.png)