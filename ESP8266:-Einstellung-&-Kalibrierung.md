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