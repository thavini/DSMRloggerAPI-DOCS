# Selecteren compiler opties

### Overzicht te selecteren functies <a id="overzicht-te-selecteren-functies"></a>

Tijdens het compileren van de firmware kun je bepaalde functionaliteit in- en uit-schakelen door de \#defines wél of níet door twee slashes \("//"\) vooraf te laten gaan.

In onderstaande tabel kun je zien of een bepaalde functionaliteit beschikbaar is voor de verschillende versies van de DSMR-logger.

<table>
  <thead>
    <tr>
      <th style="text-align:left">#define</th>
      <th style="text-align:left">Functie</th>
      <th style="text-align:left">Optioneel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="define-is_esp12.md">USE_REQUEST_PIN</a>
      </td>
      <td style="text-align:left">Geeft aan of je de firmware voor een ESP12 of andere (ESP-01) processor
        compileren</td>
      <td style="text-align:left">NEE</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_update_server.md">USE_UPDATE_SERVER</a>
      </td>
      <td style="text-align:left">Met de Update Server kun je vanuit de FSexplorer updates van de firmware
        installeren</td>
      <td style="text-align:left">JA</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-has_oled_ssd1306.md">HAS_OLED_SSD1306</a>
      </td>
      <td style="text-align:left">Functionaliteit om (status) meldingen naar een OLED scherm (0.96&quot;
        type SSD1306) te sturen</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>Niet in combinatie met HAS_OLED_SH1106</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-has_oled_sh1106.md">HAS_OLED_SH1106</a>
      </td>
      <td style="text-align:left">Functionaliteit om (status) meldingen naar een OLED scherm (1.3&quot;
        type SH1106) te sturen</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>Niet in combinatie met HAS_OLED_SSD1306</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_belgium_protocol.md">USE_BELGIUM_PROTOCOL</a>
      </td>
      <td style="text-align:left">Voor Belgische Slimme Meters</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>Niet in combinatie met USE_PRE40_PROTOCOL</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_pre40_protocol.md">USE_PRE40_PROTOCOL</a>
      </td>
      <td style="text-align:left">Voor &quot;oude&quot; Slimme Meters</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>Niet in combinatie met USE_BELGIUM_PROTOCOL</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_ntp_time.md">USE_NTP_TIME</a>
      </td>
      <td style="text-align:left">Gebruik de tijd van een NTP server i.p.v. die van de Slimme Meter</td>
      <td
      style="text-align:left">
        <p>JA</p>
        <p>alleen in combinatie met USE_PRE40_PROTOCOL</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-sm_has_no_fase_info.md">SM_HAS_NO_FASE_INFO</a>
      </td>
      <td style="text-align:left">Sommige &#xE9;&#xE9;n fase Slimme Meter&apos;s geven geen info per fase
        af</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>alleen in combinatie met USE_BELGIUM_PROTOCOL of USE_PRE40_PROTOCOL</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_mqtt.md">USE_MQTT</a>
      </td>
      <td style="text-align:left">Deze optie zorgt ervoor dat de functionaliteit voor het versturen van
        gegevens naar een MQTT broker wordt ingebouwd</td>
      <td style="text-align:left">JA</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-use_mindergas.md">USE_MINDERGAS</a>
      </td>
      <td style="text-align:left">Deze optie zorgt ervoor dat de functionaliteit voor het versturen van
        gegevens naar <a href="https://mindergas.nl/">mindergas.nl</a> waar je huidige
        gasverbruik kunt vergelijken met vorig jaar.</td>
      <td style="text-align:left">JA</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="use_syslogger.md">USE_SYSLOGGER</a>
      </td>
      <td style="text-align:left">Met de System logger is het mogelijk om debug informatie over de werking
        van de DSMR-logger op te slaan in een bestand van 500 regels.</td>
      <td style="text-align:left">JA</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-show_passwrds.md">SHOW_PASSWORDS</a>
      </td>
      <td style="text-align:left">Of je de gebruikte passwords in het Systeem Info scherm en via telnet
        wilt tonen</td>
      <td style="text-align:left">JA</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="define-has_no_meter.md">HAS_NO_METER</a>
      </td>
      <td style="text-align:left">Als je geen Slimme Meter op de DSMR-logger hebt aangesloten</td>
      <td style="text-align:left">
        <p>JA</p>
        <p>alleen om te testen</p>
      </td>
    </tr>
  </tbody>
</table>```text

/******************** compiler options  ********************************************/
#define IS_ESP12                  // define if it's a 'bare' ESP-12 (no reset/flash functionality on board)
#define USE_UPDATE_SERVER         // define if there is enough memory and updateServer to be used
#define HAS_OLED_SSD1306          // define if a 0.96" OLED display is present
//  #define HAS_OLED_SH1106           // define if a 1.3" OLED display is present
//  #define USE_BELGIUM_PROTOCOL      // define if Slimme Meter is a Belgium Smart Meter
//  #define USE_PRE40_PROTOCOL        // define if Slimme Meter is pre DSMR 4.0 (2.2 .. 3.0)
//  #define USE_NTP_TIME              // define to generate Timestamp from NTP (Only Winter Time for now)
//  #define SM_HAS_NO_FASE_INFO       // if your SM does not give fase info use total delevered/returned
//  #define HAS_NO_SLIMMEMETER        // define for testing only!
#define USE_MQTT                  // define if you want to use MQTT
#define USE_MINDERGAS             // define if you want to update mindergas (also add token down below)
//  #define USE_SYSLOGGER             // define if you want to use the sysLog library for debugging
//  #define SHOW_PASSWRDS             // well .. show the PSK key and MQTT password, what else?
/******************** don't change anything below this comment **********************/

```

