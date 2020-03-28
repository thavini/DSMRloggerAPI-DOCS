# Integratie met Home Assistant

Om in Home Assistant de gegevens uit de DSMR-logger \(met de **DSMRloggerAPI** firmware\) te gebruiken heb ik het **`configuration.yaml`** bestand als volgt aangepast:

```text
# Configure a default setup of Home Assistant (frontend, api, etc)
default_config:

# Uncomment this if you are using SSL/TLS, running in Docker container, etc.
# http:
#   base_url: example.duckdns.org:8123

# Text to speech
tts:
  - platform: google_translate

group: !include groups.yaml
automation: !include automations.yaml
script: !include scripts.yaml
scene: !include scenes.yaml

# koppeling met de DSMR-logger
sensor:
  - platform: mqtt
    name: "Gebruik"
    state_topic: "DSMR-PRD/power_delivered" 
    unit_of_measurement: "kWh"
    value_template: '{{ value_json.power_delivered[0].value | round(3) }}'

  - platform: mqtt
    name: "Laatste Update mqtt"
    state_topic: "DSMR-PRD/timestamp" 
#   value_template: '{{ value_json.timestamp[0].value }}'
    value_template: >
      {{      value_json.timestamp[0].value[4:6] + "-" + 
              value_json.timestamp[0].value[2:4] + "-" + 
         "20"+value_json.timestamp[0].value[0:2] + "   " + 
              value_json.timestamp[0].value[6:8] + ":" + 
              value_json.timestamp[0].value[8:10] + ":" + 
              value_json.timestamp[0].value[10:13] }}

  - platform: mqtt
    name: "Gebruik l1"
    state_topic: "DSMR-PRD/power_delivered_l1"
    unit_of_measurement: 'Watt'
    value_template: "{{ (value_json.power_delivered_l1[0].value | float * 1000.0) | round(1) }}"

  - platform: mqtt
    name: "Gebruik l2"
    state_topic: "DSMR-PRD/power_delivered_l2"
    unit_of_measurement: 'Watt'
    value_template: "{{ (value_json.power_delivered_l2[0].value | float * 1000.0) | round(1) }}"

  - platform: mqtt
    name: "Gebruik l3"
    state_topic: "DSMR-PRD/power_delivered_l3"
    unit_of_measurement: 'Watt'
    value_template: "{{ (value_json.power_delivered_l3[0].value | float * 1000.0) | round(1) }}"


  - platform: rest
    name: "Levering"
    resource: http://192.168.2.106/api/v1/sm/fields/power_returned
    unit_of_measurement: "kWh"
    value_template: '{{ value_json.fields[1].value | round(3) }}'

  - platform: rest
    name: "Laatste Update restAPI"
    resource: http://192.168.2.106/api/v1/sm/fields/timestamp
#   value_template: '{{ value_json.fields[0].value }}'
    value_template: >
      {{      value_json.fields[0].value[4:6] + "-" + 
              value_json.fields[0].value[2:4] + "-" + 
         "20"+value_json.fields[0].value[0:2] + "   " + 
              value_json.fields[0].value[6:8] + ":" + 
              value_json.fields[0].value[8:10] + ":" + 
              value_json.fields[0].value[10:13] }}

  - platform: rest
    name: "Levering l1"
    resource: http://192.168.2.106/api/v1/sm/fields/power_returned_l1
    unit_of_measurement: "Watt"
    value_template: '{{ (value_json.fields[1].value | float * 1000.0) | round(1) }}'

  - platform: rest
    name: "Levering l2"
    resource: http://192.168.2.106/api/v1/sm/fields/power_returned_l2
    unit_of_measurement: 'Watt'
    value_template: '{{ (value_json.fields[1].value | float * 1000.0) | round(1) }}'

  - platform: rest
    name: "Levering l3"
    resource: http://192.168.2.106/api/v1/sm/fields/power_returned_l3
    unit_of_measurement: 'Watt'
    value_template: '{{ (value_json.fields[1].value | float * 1000.0) | round(1) }}'

```

De power\_delivered velden worden via MQTT uitgelezen. De power\_returned via de restAPI's.

Dit is het resultaat:

![](.gitbook/assets/ha_restapi%20%281%29.png)

{% hint style="warning" %}
Merk op dat de resource bij de restAPI's het IP adres van de DSMR-logger gebruiken. Ik krijg het in mijn opzet niet voor elkaar hier de hostname \(dsmr-api.local\) te gebruiken.
{% endhint %}

