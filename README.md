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
Jedná se 4-ciferný 7-segmentový displej s dvoutečkou pro zobrazení času. V našem projektu dvojtečku potřebovat, ale je dobré vědět že ji můžete použít při projektech vlastních. S modulem se komunikuje za pomocí sériové komunikace přes dva kabely. Tato forma komunikace je velmi složitá, a proto pro jednoduchost budeme používat externí knihovnu.

# I2C
Inter-Integrated Circuit je sériový komunikační protokol používaný pro komunikaci mezi mikrocontroly nebo jinými elektronickými součástkami v elektronických systémech. I2C je určen pro komunikaci mezi dvěma nebo více zařízeními, která jsou propojena pomocí dvou vedení: Master-out/Slave-out (SCL) a Serial Data Line (SDA). 

Přenos dat se zahajuje START bitem (S), když je SDA nízká, zatímco SCL zůstává vysoká. Pak, SDA nastaví přenášený bit zatímco SCL je nízká (modrá) a jsou odebrány vzorky dat (přijaté) při SCL stoupá (zelená). Když je přenos dokončen, je poslaný STOP bit (P) pro uvolnění datové linky, změnou SDA na vysokou, zatímco SCL je trvale vysoký. Aby se zabránilo falešně detekci, je úroveň na SDA změněn na negativní hraně a je zachycen na kladné hrany SCL.

# Zapojení
![zapojení](https://github.com/prokyber/r-duino-led-temperature-sensor/blob/main/img/teplomer_schema.png)
