# HAS\_NO\_METER

Om te testen of de verwerking van de gegevens, die normaal gesproken uit de Slimme Meter komen, goed gaat kun je met deze \#define de firmware zó maken dat hij zélf voor \(test\) data zorgt. Om de tijd te versnellen zal de testdata eerst de maanden versneld laten voorbij gaan, daarna de dagen en tenslotte de uren.

{% hint style="warning" %}
Let op!   
Alleen om te testen!
{% endhint %}

| \#define | Functie |
| :--- | :--- |
| HAS\_NO\_METER | De DSMRloggerAPI firmware zorgt zelf voor test-data. Als deze functionaliteit actief is moet de DSMR-logger **niet** op een Slimme Meter worden aangesloten! |

