# DSMR-logger gerelateerde restAPI's

{% api-method method="get" host="http://dsmr-api.local" path="/api/v1/dev/info" %}
{% api-method-summary %}
informatie over de DSMR-logger
{% endapi-method-summary %}

{% api-method-description %}
Deze restAPI geeft informatie terug van de DSMR-logger
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Succes
{% endapi-method-response-example-description %}

```
{"devinfo":[
    {"name": "author", "value": "Willem Aandewiel (www.aandewiel.nl)"},
    {"name": "hostname", "value": "DSMR-108"},
    {"name": "fwversion", "value": "v0.2.9 (31-01-2020)"},
    {"name": "compiled", "value": "Jan 31 2020 12:22:10"},
    {"name": "freeheap", "value": 16224, "unit": "bytes"},
    {"name": "maxfreeblock", "value": 15400, "unit": "bytes"},
    {"name": "chipid", "value": "cc6156"},
    {"name": "coreversion", "value": "2_6_3"},
    {"name": "sdkversion", "value": "2.2.1(cfd48f3)"},
    {"name": "cpufreq", "value": 80, "unit": "MHz"},
    {"name": "sketchsize", "value": 521.953, "unit": "kB"},
    {"name": "freesketchSpace", "value": 1524.000, "unit": "kB"},
    {"name": "flashchipid", "value": "00164020"},
    {"name": "flashchipsize", "value": 4.000, "unit": "MB"},
    {"name": "flashchiprealsize", "value": 4.000, "unit": "MB"},
    {"name": "flashchipspeed", "value": 80.000, "unit": "MHz"},
    {"name": "flashchipmode", "value": "DOUT"},
    {"name": "boardtype", "value": "ESP8266_GENERIC"},
    {"name": "ssid", "value": "YourWiFi"},
    {"name": "ipaddress", "value": "192.168.1.106"},
    {"name": "wifirssi", "value": -52},
    {"name": "hostname", "value": "DSMR-API"},
    {"name": "uptime", "value": "0(d):00(h):10"},
    {"name": "telegramcount", "value": 56},
    {"name": "telegramerrors", "value": 0},
    {"name": "mqttbroker", "value": "mosqitto.org:1883"},
    {"name": "mqttinterval", "value": 120},
    {"name": "mqttbroker_connected", "value": "yes"},
    {"name": "mindergas_response", "value": "countdown for sending"},
    {"name": "mindergas_status", "value": "@31|12:28 -> :0"},
    {"name": "reboots", "value": 6},
    {"name": "lastreset", "value": "Software/System restart"}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://dsmr-api.local" path="/api/vi/dev/time" %}
{% api-method-summary %}
Systeem Tijd
{% endapi-method-summary %}

{% api-method-description %}
Deze restAPI geeft de systeem tijd van de DSMR-logger
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Succes
{% endapi-method-response-example-description %}

```
{"devtime":[
  {"name": "time", "value": "2021-03-09 12:15:01"},
  {"name": "epoch", "value": 1615292111}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://dsmr-api.local" path="/api/v1/dev/settings" %}
{% api-method-summary %}
Instellingen
{% endapi-method-summary %}

{% api-method-description %}
Deze restAPI geeft alle, door de gebruiker muteerbare, settings terug
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Succes
{% endapi-method-response-example-description %}

```
{"settings":[
  {"name": "hostname", "value":"DSMR-API", "type": "s", "maxlen": 29},
  {"name": "ed_tariff1", "value": 0.15123, "type": "f", "min": 0, "max": 10},
  {"name": "ed_tariff2", "value": 0.17092, "type": "f", "min": 0, "max": 10},
  {"name": "er_tariff1", "value": 0.13087, "type": "f", "min": 0, "max": 10},
  {"name": "er_tariff2", "value": 0.14567, "type": "f", "min": 0, "max": 10},
  {"name": "gd_tariff", "value": 0.23456, "type": "f", "min": 0, "max": 10},
  {"name": "electr_netw_costs", "value": 24.00, "type": "f", "min": 0, "max": 100},
  {"name": "gas_netw_costs", "value": 12.00, "type": "f", "min": 0, "max": 100},
  {"name": "tlgrm_interval", "value": 10, "type": "i", "min": 1, "max": 60},
  {"name": "oled_screen_time", "value": 10, "type": "i", "min": 1, "max": 300},
  {"name": "index_page", "value":"DSMRindex.html", "type": "s", "maxlen": 49},
  {"name": "mqtt_broker", "value":"hassio.local", "type": "s", "maxlen": 101},
  {"name": "mqtt_broker_port", "value": 1883, "type": "i", "min": 1, "max": 9999},
  {"name": "mqtt_user", "value":"user", "type": "s", "maxlen": 40},
  {"name": "mqtt_passwd", "value":"password", "type": "s", "maxlen": 30},
  {"name": "mqtt_topTopic", "value":"DSMR-API", "type": "s", "maxlen": 21},
  {"name": "mqtt_interval", "value": 60, "type": "i", "min": 0, "max": 600},
  {"name": "mindergastoken", "value":"Mg6543token", "type": "s", "maxlen": 21}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://dsmr-api.local" path="/api/v1/settings/{\"name\":\"<settingVeld>\",\"value\":\"<nieuweWaarde>\"}" %}
{% api-method-summary %}
Instellingen aanpassen
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{"name":"<settingVeld>","value":"<nieuweWaarde>"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Hieronder een opsomming van de settingsVelden:

### hostname

* type: String
* maxlen: 29
* Opmerking:
  * Characters

### ed\_tariff1 \(Geleverde Energy, tarief 1\)

* type: float
* min: 0
* max: 10
* decimalen: 5

### ed\_tariff2 \(Geleverde Energy, tarief 2\)

* type: float
* min: 0
* max: 10
* Decimalen: 5

### er\_tariff1 \(Opgewekte Energy, tarief 1\)

* type: float
* min: 0
* max: 10
* Decimalen: 5

### er\_tariff2 \(Opgewekte Energy, tarief 2\)

* type: float
* min: 0
* max: 10
* Decimalen: 5

### gd\_tariff \(Gas Geleverd\)

* type: float
* min: 0
* max: 10
* Decimalen: 5

### electr\_netw\_costs \(Netwerk kosten Electra\)

* type: float
* min: 0
* max: 100
* Decimalen: 2
* Opmerking:
  * Euro's per maand

### gas\_netw\_costs \(Netwerk kosten Gas\)

* type: float
* min: 0
* max: 100
* Decimalen: 2
* Opmerking:
  * Euro's per maand

### tlgrm\_interval \(telegram Interval\)

* type: Integer
* min: 1
* max: 60
* Opmerking:
  * Seconden

### index\_page \(alternatieve index.html pagina\)

* type: String
* maxlen: 49
* Opmerking:
  * Characters
  * Default: `DSMRindex.html`

### mqtt\_broker \(URL of IP-adres\)

* type: String
* maxlen: 100
* Opmerking:
  * Characters

### mqtt\_broker\_port

* type: Integer
* min: 0
* max: 9999

### mqtt\_user

* type: String
* maxlen: 39
* Opmerking:
  * Characters

### mqtt\_passwd

* type: String
* maxlen: 29
* Opmerking:
  * Characters

### mqtt\_toptopic

* type: String
* maxlen: 20
* Opmerking:
  * Characters

### mqtt\_interval \(interval voor het versturen van MQTT berichten\)

* type: Integer
* min: 0
* max: 600
* Opmerking: Seconden
  * indien '0' worden er géén berichten verstuurd
  * er wordt nooit vaker een bericht verstuurd dan `tlgrm_interval`

### mindergastoken

* type: String
* maxlen: 20
* Opmerking:
  * Characters
  * indien korter dan 5 char's worden er geen gegevens naar `mindergas.nl` verstuurd

