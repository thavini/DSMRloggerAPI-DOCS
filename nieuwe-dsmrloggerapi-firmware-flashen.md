# Nieuwe DSMRloggerAPI firmware flashen

Nieuwe DSMRloggerAPI firmware kan via de web-interface van de DSMR-logger "_Over the Air_" geflashed worden.

{% hint style="danger" %}
Hoe je de firmware moet upgraden van _DSMRlogger**WS**_ naar _DSMRlogger**API**_ ****staat [hier](upgrade-dsmrloggerws-naar-dsmrloggerapi.md) beschreven!
{% endhint %}

### Pre compiled Binaries

Op [github](https://github.com/mrWheel/DSMRloggerAPI) staan van de major releases, voor de meest voorkomende situaties, binaries van zowel de firmware als van het SPIFFS in .zip formaat. 

![](.gitbook/assets/githubmain.png)

Klik op "[releases](https://github.com/mrWheel/DSMRloggerAPI/releases)" en download het ino.bin.zip bestand dat voor jouw situatie geschikt is \(deze staan onder iedere release beschrijving bij "_Assets_"\).

{% hint style="success" %}
Bij een gewone firmware update is het meestal niet nodig ook het SPIFFS opnieuw te downloaden en te flashen.
{% endhint %}

Onder iedere release beschrijving staan de bijbehorende "_Assets_".

![](.gitbook/assets/githubselectzip.png)

{% hint style="info" %}
In de beschrijving van de release staat met welke compiler options de verschillende binaries zijn gemaakt. Heb jij andere compiler options nodig dan zul je de sources moeten downloaden en met de Arduino IDE zelf een binary moeten maken.
{% endhint %}

Als de binary\(s\) op je computer staan dan moet je deze uitpakken \(unzippen\).

Ga nu op de DSMR-logger naar de FSexplorer \(door op het icoon ![](.gitbook/assets/fsexplorer_icon.png) te klikken\) en klik vervolgens op de knop \[Update Firmware\].

![](.gitbook/assets/fsexplorerfwupdate.png)

Klik nu op de bovenste \[Choose File\] knop 

![](.gitbook/assets/chooseino.png)

Selecteer in het popup-window het zojuist gedownloade en uitgepakte ino.bin file:

![](.gitbook/assets/updateselectfw.png)

Klik op \[Open\] of \[Select\] en klik vervolgens op de knop \[Flash Firmware\].   
Na enige tijd verschijnt het volgende scherm:

![](.gitbook/assets/updatesuccess.png)

.. waarna, als de teller op nul staat het hoofdscherm van de DSMR-logger weer verschijnt.

{% hint style="warning" %}
Alleen als in de beschrijving van een release staat dat ook SPIFFS opnieuw geflased moet worden moet u dit doen. In veel gevallen zal volstaan om eventueel een bepaald bestand naar SPIFFS te uploaden. Ook dit zal dan expliciet in de release beschrijving staan.
{% endhint %}

