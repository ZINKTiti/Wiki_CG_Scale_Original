### Übersicht

Wird für die CG scale ein AVR Mikroprozessor verwendet, sind alle relevanten Funktionen mit an Board. Bis zu drei Wäagezellen werden unterstützt, Parametrierung ist per serieller Schnittstelle möglich. Die Anzeige erfolgt durch ein OLED Display. Eine WiFi Funktion mit Webpage ist nicht vorhanden.

### Elektrischer und mechanischer Aufbau

Je nach gewünschtem Messbereich können die Wiegezellen nach belieben dimensioniert werden, solche gibt es von 1-200Kg. Die Zellen dürfen unterschiedlich gross sein. Die Messwandler der Wiegezellen müssen einen HX711 Chip enthalten. Als CPU wird grundsätzlich ein Arduino Micro mit Atmega32u4 empfohlen, andere Arduinos z.B. mit Atmega328 Prozessor sollten jedoch auch funktionieren.

#### Materialliste:

- 1x [OLED Display 1.3" 4Pin I2C White](https://www.aliexpress.com/item/1-3-Inch-OLED-Module-White-Color-128X64-OLED-LCD-LED-Display-Module-1-3-IIC/32844104782.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0)
- 1x [Arduino Micro Atmega32u4](https://www.aliexpress.com/item/New-Pro-Micro-for-arduino-ATmega32U4-5V-16MHz-Module-with-2-row-pin-header-For-Leonardo/32846843498.html?spm=2114.search0604.3.65.285440b2VeciNH&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=39fddcc3-f2cd-4c52-b20b-4a1fdba48af5-9&algo_pvid=39fddcc3-f2cd-4c52-b20b-4a1fdba48af5)
- 3x [Loadcell + HX711 AD Module](https://www.aliexpress.com/item/1kg-2kg-3kg-5kg-10kg-20kg-Weighing-Sensor-Load-Cell-Weight-Sensor-Electronic-Kitchen-Scale-HX711/32863297220.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0)
- 2x [Metall Film Resistor 10k 1%](https://www.aliexpress.com/item/100pcs-1-4W-1R-22M-1-Metal-film-resistor-100R-220R-1K-1-5K-2-2K/32847096736.html?spm=2114.search0604.3.1.1ff530c2WP491F&s=p&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=5b45da6d-ef50-42bf-9243-883fe4708342-0&algo_pvid=5b45da6d-ef50-42bf-9243-883fe4708342) (optional)


#### Elektroschema:
![schema](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_schema.png)

Werden nur zwei Wiegezellen benötigt, so wird Zelle nr. 3 weggelassen. Wird die Spannungsmessung nicht benötig, können die beiden Wiederstände R1 und R2 weggelassen werden. Werden andere Wiederstände verwendet, müssen die Werte in den Einstellungen angepasst werden.

#### Mechanische Anordnung:
![mechanic](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_mechanics.png)

Die Wiegezellen 1 + 3 dürfen auch vor dem Anschlag sein, der Wert X1 wird dann negativ eingegeben.
