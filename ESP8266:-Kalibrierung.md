### Kalibrierung

Zur Kalibrierung gibt es zwei Möglichkeiten:

#### 1. Automatisch

Anhand eines Referenzobjekts. Zum Beispiel ein Modell, von dem das genaue Gewicht und der genaue Schwerpunkt bekannt ist. Alternativ kann zB. auch eine ALU Platte verwendet werden. Die Platte sollte genau symmetrisch sein, dadurch befindet sich der Schwerpunkt der Platte genau in der Mitte. Ist das Gewicht und der Schwerpunkt von unserem Referenzobjekt bekannt, müssen diese Parameter bei **Referenz Gewicht** und **Referenz Schwerpunkt** eingegeben werden, und **Speichern** drücken. Oberhalb des Tare-Button sieht man die Einzelgewichte der Zellen, darauf achten, dass diese auf 0g stehen, andernfalls **Tare** drücken. Nun das Referenzobjekt auf die Waage legen, und **Automatisch kalibrieren** drücken. 

#### 2. Manuell

Man kalibriert anhand eines Referenzgewichts jede einzelne Wiegezelle. Das Gewicht auf eine Wiegezelle legen und den entsprechenden Kalibrierfaktor anpassen bis der angezeigte Wert mit dem Referenzgewicht übereinstimmt. Alternativ kann der Kalibrierfaktor mit folgender Formel berechnet werden:

_Kalibrierfaktor = KalFaktorAlt / (RefGewicht / IstGewicht)_

![cgscale_settings](https://github.com/nightflyer88/CG_scale/blob/master/Doc/img/cgscale_settings_mechanic.png)