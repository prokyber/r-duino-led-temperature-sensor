# Pokojový teploměr s Ř-duino-LED
Cílem tohoto projektu je vytvořit funkční vnitřní teploměr, který nám po zapojení do elektřiny bude měřit a zobrazovat ve °C, na 7-mi segmentovém displeji, teplotu místnosti. Pokud jste si na desku nahráli jiný kód, původní program je ke stažení [zde](https://github.com/prokyber/Rduino-LED).
 
# Součástky
- Ř-duino-LED
- [vodiče](https://e-shop.prokyber.cz/kabely--vodice/dupont-kabel/)  8x
- [hodinový displej TM1637](https://e-shop.prokyber.cz/vystupni/4-x-7-segmentovy-display-s-i2c/)
- [BMP180](https://e-shop.prokyber.cz/periferie-pro-mikrokontrolery/bmp-180/)
- [nepájivé pole](https://e-shop.prokyber.cz/konektory/nepajive-pole-170-pinu/)

# BMP180
Jedná se o senzor teploty, tlaku a nadmořské výšky. Je vybaven citlivým polovodičem (např. silikon), který při změně barometrického tlaku změní i svůj odpor. Tuto změnu je pak naše deska schopná zaznamenat a vypočítat z ní teplotu, přibližnou nadmořskou výšku a další jiném věci. Pro komunikaci se senzorem použijeme protocol I2C.

# TM1637
Jedná se o 4 x 7 segmentový displej s dvojtečkou pro čas. 


