# Historische Gegevens gerelateerde restAPI's

De restAPI's voor het opvragen van historische gegevens hebben dit formaat:

```text
/api/v1/hist/{hours|days|months}
```

of:

```text
/api/v1/hist/{hours|days|months}/{asc|desc}
```

{% api-method method="get" host="http://dsmr-api.local" path="/api/v1/hist/hours" %}
{% api-method-summary %}
Opvragen gegevens uit de uren tabel
{% endapi-method-summary %}

{% api-method-description %}
Geeft een JSON string met de historische gegevens over de afgelopen 24 uur terug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Succes
{% endapi-method-response-example-description %}

```
{"hours":[
  {"recnr": 0, "recid": "21031006", "slot": 17,"edt1": 2328.742, "edt2": 8500.609,"ert1": 353.507, "ert2": 196.479,"gdt": 2958.498},
  {"recnr": 1, "recid": "21031005", "slot": 16,"edt1": 2328.739, "edt2": 8500.598,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.495},
  {"recnr": 2, "recid": "21031004", "slot": 15,"edt1": 2328.735, "edt2": 8500.588,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.488},
  {"recnr": 3, "recid": "21031003", "slot": 14,"edt1": 2328.729, "edt2": 8500.563,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.481},
  {"recnr": 4, "recid": "21031002", "slot": 13,"edt1": 2328.725, "edt2": 8500.551,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.478},
  {"recnr": 5, "recid": "21031001", "slot": 12,"edt1": 2328.721, "edt2": 8500.539,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.474},
     .
     .
     .
  {"recnr": 43, "recid": "21030811", "slot": 23,"edt1": 2328.563, "edt2": 8499.973,"ert1": 353.492, "ert2": 196.472,"gdt": 2958.277},
  {"recnr": 44, "recid": "21030810", "slot": 22,"edt1": 2328.558, "edt2": 8499.949,"ert1": 353.491, "ert2": 196.471,"gdt": 2958.272},
  {"recnr": 45, "recid": "21030809", "slot": 21,"edt1": 2328.555, "edt2": 8499.940,"ert1": 353.490, "ert2": 196.471,"gdt": 2958.270},
  {"recnr": 46, "recid": "21030808", "slot": 20,"edt1": 2328.550, "edt2": 8499.921,"ert1": 353.489, "ert2": 196.471,"gdt": 2958.260},
  {"recnr": 47, "recid": "21030807", "slot": 19,"edt1": 2328.546, "edt2": 8499.904,"ert1": 353.488, "ert2": 196.470,"gdt": 2958.255},
  {"recnr": 48, "recid": "21030806", "slot": 18,"edt1": 2328.543, "edt2": 8499.895,"ert1": 353.488, "ert2": 196.470,"gdt": 2958.250}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://dsmr-api.local" path="/api/v1/hist/days" %}
{% api-method-summary %}
Opvragen gegevens uit de dagen tabel
{% endapi-method-summary %}

{% api-method-description %}
Geeft een JSON string met alle gegevens over de afgelopen 14 dagen terug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Succes
{% endapi-method-response-example-description %}

```
{"days":[
  {"recnr": 0, "recid": "21031104", "slot": 7,"edt1": 2328.828, "edt2": 8500.923,"ert1": 353.516, "ert2": 196.483,"gdt": 2958.626},
  {"recnr": 1, "recid": "21031023", "slot": 6,"edt1": 2328.810, "edt2": 8500.861,"ert1": 353.516, "ert2": 196.483,"gdt": 2958.598},
  {"recnr": 2, "recid": "21030923", "slot": 5,"edt1": 2328.712, "edt2": 8500.511,"ert1": 353.506, "ert2": 196.479,"gdt": 2958.463},
  {"recnr": 3, "recid": "21030823", "slot": 4,"edt1": 2328.616, "edt2": 8500.146,"ert1": 353.497, "ert2": 196.475,"gdt": 2958.338},
  {"recnr": 4, "recid": "21030723", "slot": 3,"edt1": 2328.513, "edt2": 8499.809,"ert1": 353.488, "ert2": 196.470,"gdt": 2958.209},
   .
   .
   .
  {"recnr": 9, "recid": "21030223", "slot": 13,"edt1": 2328.028, "edt2": 8498.042,"ert1": 353.444, "ert2": 196.446,"gdt": 2957.589},
  {"recnr": 10, "recid": "21030123", "slot": 12,"edt1": 2327.934, "edt2": 8497.677,"ert1": 353.435, "ert2": 196.441,"gdt": 2957.457},
  {"recnr": 11, "recid": "21022823", "slot": 11,"edt1": 2327.651, "edt2": 8496.564,"ert1": 353.407, "ert2": 196.428,"gdt": 2957.076},
  {"recnr": 12, "recid": "21022723", "slot": 10,"edt1": 2327.560, "edt2": 8496.223,"ert1": 353.400, "ert2": 196.424,"gdt": 2956.947},
  {"recnr": 13, "recid": "21022623", "slot": 9,"edt1": 2327.472, "edt2": 8495.822,"ert1": 353.391, "ert2": 196.419,"gdt": 2956.831},
  {"recnr": 14, "recid": "21022523", "slot": 8,"edt1": 2327.383, "edt2": 8495.460,"ert1": 353.383, "ert2": 196.415,"gdt": 2956.704}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://dsmr-api.local" path="/api/v1/hist/months" %}
{% api-method-summary %}
Opvragen gegevens uit de maanden tabel
{% endapi-method-summary %}

{% api-method-description %}
Geeft een JSON string met alle gegevens van de afgelopen 24 maanden terug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{"months":[
  {"recnr": 0, "recid": "21031106", "slot": 18,"edt1": 2328.836, "edt2": 8500.952,"ert1": 353.517, "ert2": 196.484,"gdt": 2958.637},
  {"recnr": 1, "recid": "21022823", "slot": 17,"edt1": 2327.651, "edt2": 8496.564,"ert1": 353.407, "ert2": 196.428,"gdt": 2957.076},
  {"recnr": 2, "recid": "21013023", "slot": 16,"edt1": 2324.980, "edt2": 8486.277,"ert1": 353.170, "ert2": 196.306,"gdt": 2953.531},
  {"recnr": 3, "recid": "20123023", "slot": 15,"edt1": 2322.095, "edt2": 8475.463,"ert1": 352.912, "ert2": 196.175,"gdt": 2949.813},
  {"recnr": 4, "recid": "20113023", "slot": 14,"edt1": 2319.278, "edt2": 8464.555,"ert1": 352.654, "ert2": 196.047,"gdt": 2946.054},
  {"recnr": 5, "recid": "20103023", "slot": 13,"edt1": 2316.394, "edt2": 8453.577,"ert1": 352.392, "ert2": 195.919,"gdt": 2942.263},
   .
   .
   .
  {"recnr": 19, "recid": "19083023", "slot": 24,"edt1": 2276.118, "edt2": 8300.609,"ert1": 348.744, "ert2": 194.109,"gdt": 2889.412},
  {"recnr": 20, "recid": "19073023", "slot": 23,"edt1": 2273.252, "edt2": 8289.574,"ert1": 348.484, "ert2": 193.979,"gdt": 2885.693},
  {"recnr": 21, "recid": "19063023", "slot": 22,"edt1": 2270.319, "edt2": 8278.475,"ert1": 348.228, "ert2": 193.847,"gdt": 2881.936},
  {"recnr": 22, "recid": "19053023", "slot": 21,"edt1": 2267.456, "edt2": 8267.560,"ert1": 347.971, "ert2": 193.718,"gdt": 2878.164},
  {"recnr": 23, "recid": "19042918", "slot": 20,"edt1": 2264.495, "edt2": 8256.316,"ert1": 347.702, "ert2": 193.585,"gdt": 2874.242},
  {"recnr": 24, "recid": "19033023", "slot": 19,"edt1": 2261.732, "edt2": 8245.799,"ert1": 347.443, "ert2": 193.461,"gdt": 2870.651}
]}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

