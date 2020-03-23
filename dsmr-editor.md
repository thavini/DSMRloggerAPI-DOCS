# DSMR-editor

De DSMRloggerAPI heeft de mogelijkheid om meterstanden en instellingen via de browser te veranderen.

Je start de **`DSMR-editor`** door in het hoofdscherm op het ![](.gitbook/assets/settings.png) icoontje te klikken.

![](.gitbook/assets/settingseditorstart.png)

Betekenis van de knoppen:

* **Terug**: Terug naar het hoofdscherm van de DSMR-logger
* **Meterstanden**: Hier kunnen, per maand, de meterstanden worden ingevoerd. Er kan gekozen worden tussen de meterstanden van de gebruikte energie, de opgewekte energie en het gas verbruik.
* **Settings**: Hier kunnen bepaalde parameters zoals de energie tarieven, interval voor het lezen van telegrammen, gegevens van de MQTT broker en het autorisatie token van Mindergas.nl worden ingesteld.
* **Herstel**: ingevoerde veranderingen die nog niet zijn opgeslagen worden teniet gedaan.
* **Opslaan**: de ingevoerde gegevens worden opgeslagen

### Meterstanden aanpassen

![](.gitbook/assets/editdata.png)

Het muteren van de maanden tabel is nog niet helemaal zoals het zou moeten zijn. Het is vrij lastig omdat de software zeker moet zijn dat de _jaar/maand_ gegevens, van boven naar beneden, _aflopen en aansluiten_ en ook de meterstanden moeten _een steeds lagere waarde_ hebben. Wordt niet aan voorgaande inter-validatie voldaan, dan kleurt het vakje waar de fout is ontdekt rood en worden de gegevens **niet** opgeslagen.

### Settings aanpassen

![](.gitbook/assets/editsettings.png)



#### Hostname

De default Hostname is DSMR-API. De documentatie gaat ook uit van deze default hostname. Mocht je de hostnaam hier veranderen dan moet je bij het lezen van de documentatie overal "DSMR-API" vervangen door de hier ingevoerde hostnaam.

#### Telegram Lees Interval

Default interval is 10. Dit betekent dat er iedere tien seconden een interval wordt gelezen en verwerkt. De minimum waarde is 2 seconden.

#### Te gebruiken index.html pagina

De standaard index pagina is "_DSMRindex.html_". Mocht je zelf een GUI schrijven dan kun je hier de naam van de index pagina van jouw GUI invullen. Standaard staan er ook een **DSMRindexEDGE.html** en een **ADJindex.html** pagina op SPIFFS. De eerste variant is gelijk aan de _DSMRindex.html_ pagina maar hij haalt de _javascript_ en _css_ bestanden uit de github repository zodat aanpassingen \(uitbreidingen of verbeteringen\) automatisch door de DSMR-logger gebruikt worden. Het **ADJindex.html** bestand is een bootstrap naar de door [Arjen de Jong](https://github.com/arjendejong12/DSMRloggerGUI) gemaakte GUI.

{% hint style="warning" %}
Een nieuw ingevoerde index pagina wordt pas actief na het opnieuw opstarten van de DSMR-logger \(\[ReBoot\] knop in de FSexplorer\).
{% endhint %}

#### Verzend MQTT berichten

Hier kun je opgeven hoe vaak de DSMR-logger een bericht naar de MQTT broker moet sturen. Voer je hier '0' \(nul\) in dan worden er géén berichten naar de MQTT broker verstuurd. Een waarde kleiner dan de _Telegram Lees Interval_ zorgt ervoor dat na ieder gelezen telegram een bericht naar de MQTT broker wordt verstuurd.

![](.gitbook/assets/dsmr_api_kosten.png)

