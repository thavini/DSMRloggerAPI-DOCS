# HAS\_OLED\_SH1106

Als je een SH1106 OLED schermpje op **J4** van de DSMR-logger V4 hebt aangesloten dan zorgt deze optie ervoor dat het OLED schermpje ook gebruikt wordt door de Firmware. Dit scherm is aanzienlijk groter en beter af te lezen dan de 0.96" schermpjes.

{% hint style="info" %}
Met dank aan Dick Spork.
{% endhint %}

| \#define | Functie |
| :--- | :--- |
| USE\_OLED\_SH1106 | Deze define zorgt ervoor dat het 1.3" OLED schermpje gebruikt wordt om meldingen op te presenteren. Deze define kan niet in combinatie met **HAS\_OLED\_SSD1306** worden gebruikt! |

![](https://mrwheel.github.io/DSMRloggerWS/img/SH1106_Display.png)

