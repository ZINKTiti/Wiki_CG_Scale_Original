### Übersicht

Wird für die CG scale ein ESP8266 Mikroprozessor verwendet, ist eine WiFi Funktion mit grafischer Webpage an Board. Bis zu drei Wäagezellen werden unterstützt, die Einstellungen werden komfortabel per Webpage vorgenommen. Die Anzeige erfolgt optional durch ein OLED Display. Per Webpage gibt es erweiterte Funktionen wie virtuelle Gewichte, speichern von Modellen, usw.

### Aufbau

Je nach gewünschtem Messbereich können die Wiegezellen nach belieben dimensioniert werden, solche gibt es von 1-200Kg. Die Zellen dürfen unterschiedlich gross sein. Die Messwandler der Wiegezellen müssen einen HX711 Chip enthalten. Als CPU wird ein Node MCU V1.0 mit ESP8266 Chip empfohlen.

#### Materialliste:

- 1x [OLED Display 1.3" 4Pin I2C White](https://www.aliexpress.com/item/1-3-Inch-OLED-Module-White-Color-128X64-OLED-LCD-LED-Display-Module-1-3-IIC/32844104782.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0) (optional)
- 1x [NodeMcu ESP8266 CP2102](https://www.aliexpress.com/item/New-Wireless-module-NodeMcu-Lua-WIFI-Internet-of-Things-development-board-based-ESP8266-with-pcb-Antenna/1967836272.html?spm=2114.search0104.3.280.484563a8cswkJr&ws_ab_test=searchweb0_0,searchweb201602_3_10065_10068_319_10059_10884_317_10887_10696_321_322_10084_453_10083_454_10103_10618_10307_537_536_10902_10134,searchweb201603_57,ppcSwitch_0&algo_expid=8ffca336-38fc-429c-9530-e23d73a407b9-37&algo_pvid=8ffca336-38fc-429c-9530-e23d73a407b9&transAbTest=ae803_3)
- 3x [Loadcell + HX711 AD Module](https://www.aliexpress.com/item/1kg-2kg-3kg-5kg-10kg-20kg-Weighing-Sensor-Load-Cell-Weight-Sensor-Electronic-Kitchen-Scale-HX711/32863297220.html?spm=a2g0s.9042311.0.0.2d694c4dpt13y0)
- 1x [Metall Film Resistor 10k 1%](https://www.aliexpress.com/item/100pcs-1-4W-1R-22M-1-Metal-film-resistor-100R-220R-1K-1-5K-2-2K/32847096736.html?spm=2114.search0604.3.1.1ff530c2WP491F&s=p&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=5b45da6d-ef50-42bf-9243-883fe4708342-0&algo_pvid=5b45da6d-ef50-42bf-9243-883fe4708342) (optional)
- 1x [Metall Film Resistor 20k 1%](https://www.aliexpress.com/item/100pcs-1-4W-1R-22M-1-Metal-film-resistor-100R-220R-1K-1-5K-2-2K/32847096736.html?spm=2114.search0604.3.1.1ff530c2WP491F&s=p&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_319_10059_10884_317_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_431_10307_537_536_10134,searchweb201603_2,ppcSwitch_0&algo_expid=5b45da6d-ef50-42bf-9243-883fe4708342-0&algo_pvid=5b45da6d-ef50-42bf-9243-883fe4708342) (optional)

#### Mechanik

Es gibt unzählige Varianten wie die Waage mechanisch aufgebaut wird. Ob mit fester oder verschiebbarer Auflagefläche, einzelne frei bewegliche Messzellen für unter das Fahrwerk, und und und... 

Als Beispiel gibt es hier einigen Varianten zum 3D-Drucken:
- [CG Scale - printed parts by claustonnesen](https://www.thingiverse.com/thing:3610084)
- [CG scale by Riboga](https://www.thingiverse.com/thing:3711368)
- [Another CG Scale by stefan089](https://www.thingiverse.com/thing:4637811)

Oder eine Version gefräst aus Sperrholz:

![CG Scale](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/img/CG_Scale_wood.jpeg)

**Mechanische Anordnung:**

Die Wiegezellen 1 + 3 dürfen auch vor dem Anschlag sein, der Wert X1 wird dann negativ eingegeben.

![mechanic](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_mechanics.png)

#### Elektronik

Die Elektronik wird nach folgendem Schema zusammengelötet:
![schema](https://raw.githubusercontent.com/nightflyer88/CG_scale/master/Doc/CG_scale_schema_ESP8266.png)

Werden nur zwei Wiegezellen benötigt, so wird Zelle nr. 3 weggelassen. Wird die Spannungsmessung nicht benötig, können die beiden Widerstände R1 und R2 weggelassen werden. Werden andere Wiederstände verwendet, müssen die Werte in den Einstellungen angepasst werden.

Als Spannungsversorgung kann zB. ein 1S oder 2S LiPo verwendet werden. Die Widerstände R1 und R2 müssen entsprechend der maximalen Versorgungsspannung dimensioniert werden. Folgende Tabelle hilft bei der Auswahl:

| max. Spannung | R1  | R2  |
|--------------|-----|-----|
| 9.9V         | 20K | 10K |
| 6.6V         | 10K | 10K |
| 3.3V         | -   | -   |

Bei einigen Boards sind bereits Spannungsteiler- oder Vorwiderstände auf der Platine verbaut, dies kann die Spannungsmessung verfälschen. Ein blick ins Schema des jeweiligen Boards hilft dabei. 

Die Widerstände haben in der Regel eine Toleranz von 5%, entsprechen kann später die Spannungsanzeige abweichen. Um die Genauigkeit zu erhöhen, misst man die Widerstände (in nicht eingelötetem Zustand) mit einem Multimeter und notiert sich die effektiven Werte.