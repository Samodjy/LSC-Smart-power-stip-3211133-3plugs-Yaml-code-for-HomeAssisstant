# LSC-Smart-power-stip-3211133-3plugs-Yaml-code-for-HomeAssisstant
This code is for the power stip from ACTION. Control individual plugs with Home Assisstant.


----------------------------------------------Disclamer----------------------------------------------

As usual, 

electricity = danger = ZAP = Dead 

don't try a get in the past, you'll never get 1.21Gigowatt from you house outlet. Nice try..

Not my bad if you burn you house, your dog, you grandma etc etc...

Be smart, dont die.


---------------------------------------------Basic intro---------------------------------------------

You'll need all the process usual to upload a new firmware in the powerstrip.
Using a TTL to USB following the PinOut from the CBU board:

https://docs.libretiny.eu/boards/cbu/cbu.svg

I followed the nice tuto from jiquintar made for a simple smart plug (essentially the same path):

https://forum.hacf.fr/t/tuto-lsc-action-power-plug-methode-pour-les-passer-sous-esphome/55780

and using (as well as in the tuto) itchiptool:

https://github.com/libretiny-eu/ltchiptool


-----------------------------------------------PinOUT-----------------------------------------------


Here is the pinout that i've found with my multimeter and with the package info of the CBU:

(description  /  package pin  / gpio number        ---- usage ?)

CF (BL0937)  /  pin 1  /  gpio14

WifiLedStat  /  pin 2  /  gpio16

RelayLed3  /  pin 5  /  gpio22

RelayLed2  /  pin 8  /  gpio8

Relay 1  /  pin 9  / gpio7

relay 2  /  pin 10  /  gpio 6

RelayLed1  /  pin 11  /  gpio26

relay 3  /  pin 12  /  gpio24

GND  /  pin 13  /  xxxxx     ---- connect to TTL GND

VCC /  pin 14  /  xxxx 3.3v!!!      ---- connect to TTL VCC 3.3V!!!!

TX  /  pin 15  /  xxxx              ---- connect to TTL RX

RX  /  pin 16  /  xxxx              ---- connect to TTL TX

CEN  /  pin 18  /  xxxx             ---- connect to GND for BOOTLOAD mode 

CF1 (BL0937)  /  pin 19  /  gpio9

SEL (BL0937)  /  pin 20  /  gpio17

Physical button  /  pin 21  /  gpio15


-------------------------------------------------More-------------------------------------------------


To be sure that i'm in bootmode, i simply "read chip info" befor trying to upload the new firmware.

I strictly don't know if it's a good or stupid idea. But i deleted in the code my API key, etc etc, just get them from your own HA.

------------------------------------------------fonctions----------------------------------------------

-Startup All relay off 

-relay on = led on

-wifi led blinkin when booting and no wifi

-wifi led solid when all is ok

-Button fuction : 1 click all relay ON
                  2 click (350ms) all relay off


-----------------------------------------------credit--------------------------------------------------

To all the dudes that have wrote some code that i used, and chatGPT

1/https://forum.hacf.fr/t/tuto-lsc-action-power-plug-methode-pour-les-passer-sous-esphome/55780

Those guys
2/https://keetsupport.nl/2024/03/20/how-to-flash-lsc-power-plug-with-esphome/

And certainely other guys that i've forget.

Cheers.

Samodjy

