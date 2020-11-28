### Parameter Einstellungen

Die Parameter werden per serieller Schnittstellen parametriert. Das Arduino Board per USB am Computer anschliessen, und unter Werkzeuge das entsprechende Board sowie Port auswählen. Danach den Seriellen Monitor öffnen.

**Werkzeuge > Serieller Monitor**

![open_serial_monitor](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/open_serial_monitor.png)

Ab Version 2.x die Baudrate auf 115200 einstellen, bei älteren Versionen auf 9600. Es erscheint nun ein simples Text Menü. Man gibt die Menünummer ein (mit Enter bestätigen), und es erscheint der entsprechende Wert den man ändern möchte.

![menu](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/serial_menu.png)

Zuerst müssen die mechanischen Dimensionen definiert werden, also Menü 1-4. Die Batteriespannung wird mit den Menüs 11-13 eingestellt. Alle Parameter werden im internen EEprom gespeichert und gehen auch nach einem Softwareupdate nicht verloren.


### Kalibrierung

Zur Kalibrierung gibt es zwei Möglichkeiten:

#### 1. Manuell

Man kalibriert anhand eines Referenzgewichts jede einzelne Wiegezelle. Das Gewicht auf eine Wiegezelle legen und den entsprechenden Kalibrierfaktor anpassen (Menü 8-10) bis der angezeigte Wert mit dem Referenzgewicht übereinstimmt. Die Werte der einzelnen Wiegezellen werden unter Menü 12 angezeigt. Alternativ kann der Kalibrierfaktor mit folgender Formel berechnet werden:

_Kalibrierfaktor = KalFaktorAlt / (RefGewicht / IstGewicht)_

#### 2. Automatisch

Anhand eines Referenzobjekts. Zum Beispiel ein Modell, von dem das genaue Gewicht und der genaue Schwerpunkt bekannt ist. Alternativ kann auch ein Brett mit einem Gewicht verwendet werden. Das Brett sollte symmetrisch sein und das Gewicht mittig auf dem Brett positioniert sein. Ist das Gewicht und der Schwerpunkt von unserem Referenzobjekt bekannt, müssen diese Parameter in Menü 5 und 6 eingegeben werden. Nun das Referenzobjekt auf die Waage legen, und unter Menü 7 den Kalibriervorgang starten. 
