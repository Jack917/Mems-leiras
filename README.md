# Mems-leiras
A mi "projektünk" egy Hordozható Retro játék konzol egy emulátor program (RetroPie) felhasználásával.

Ez alapján kötöttük be a pin-eket a joystick-ba:


![gaming_joy-pins2](https://user-images.githubusercontent.com/44037717/51151015-40d75f80-1869-11e9-9d94-d802bfe57cd3.png)


Ez alapján kötöttük be a raspberry pin-jeibe a a gombokat és a joystick-et:


![pinout](https://user-images.githubusercontent.com/44037717/51151043-6e240d80-1869-11e9-82c7-05c9f8836d00.png)


RetroPie felállításához szükséges script-ek:

-A Schellscript ami elindítja a RetroArch nevű emulátort:
https://github.com/RetroPie/RetroPie-Setup

-Letöltöttük a legújabb RetroPie telepítőt
git clone --depth=1 https://github.com/RetroPie/RetroPie-Setup.git

-Felraktuk a RetroPie-t
sudo ./retropie_setup.sh

-Ezután a RetroPie roms mappáján belül játékokat tölthetünk le, a zip fájlt elhelyezzük a mappában.

-A program ami a pin-eket virtuális billentyűnek érzékeli:
https://github.com/adafruit/Adafruit-Retrogame

-A program telepítése után következett a gombok konfigurálása. Ezután lehetővé kell tenni, hogy az emulátor megfelelően működjön.
sudo nano /etc/udev/rules.d/10-retrogame.rules

-A fájlba beillesztjük a következő parancsot:
SUBSYSTEM=="input", ATTRS{name}=="retrogame", ENV{ID_INPUT_KEYBOARD}="1"

-Majd elindíthatjuk a retrogame-t és játszhatunk

sudo ./retrogame


Segítségek a feladat elkészítéséhez:

https://learn.adafruit.com/retro-gaming-with-raspberry-pi

https://www.youtube.com/watch?v=bYHXUECdQAg&t=917s


https://www.youtube.com/watch?v=xvYX_7iRRI0



Linkek a fő alkatrészekhez:

A gombok:
https://www.amazon.com/gp/product/B01MYWADYZ/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B01MYWADYZ&linkCode=as2&tag=hackerhouse-20&linkId=8290fd53e2ce93002037107d879593ed

A Joystick:
https://www.ebay.com/itm/Sanwa-Original-Japan-Arcade-Joystick-JLF-TP-8YT-with-Green-Ball-Top-stick-mod-/181514275628?hash=item2a43180b2c

Raspberry Pi:
https://www.amazon.com/gp/product/B01CD5VC92/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B01CD5VC92&linkCode=as2&tag=hackerhouse-20&linkId=3b684c0f652962f29c089c0a9bfb6032

Kábelek:
https://www.adafruit.com/product/266
