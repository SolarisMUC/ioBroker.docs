![Logo](media/tradfri.png)
Ikea tradfri Adapter
=============

| Stand der Doku | 10.01.2019                      |
|----------------|---------------------------------|
| Entwickler     | AlCalzone            	   |
| Kategorie      | ioT Systeme                     |
| Keywords       | Ikea, Tradfri, SmartHome |
| Abhängigkeiten |                                 |
| Lizenz         | MIT                             |

Tradfri
---------

Tradfri ist ein SmartHome System der Firma Ikea. Zum jetzigen Zeitpunkt umfasst
dieses System verschiedenste Komponenten aus:

- Leuchtmittel(Lampen)
- LED-Panele/Leisten für Wände und Schränke/Schranktüren
- Bewegungsmelder
- Rolläden für Fenster
- Fernbedienung
- zentraler Gateway

Das Tradfri System ist somit eines der umfangreichesten SmartHome Komponentensystem
was es momentan auf dem Markt gibt.

Voraussetzungen zur Verwendung von Tradfri mit ioBroker
---------------------------------------------------------------

- RaspberryPi 3 Model B+
- Tradfri Gateway
- Tradfri Komponenten (z.b. Leuchtmittel oder Bewegungsmelder etc.)
- Tradfri Fernbedienung


Verwaltung und Steuerung von Tradfri mit ioBroker
---------------------------------------------------------------

Um Tradfri mit ioBroker optimal zu verwalten und zu steuern
wird folgender Adapter benötigt:

1.  Ikea Tradfri

Dieser Adapter stellt eine Verbindung zum zentralen Tradfri Gateway her
Er synchronisiert Komponenten(Lampen, Bewegungsmelder etc.), Szenen, Systemvariablen 
Tradfri Gateway und ioBroker. Abb. 01 zeigt eine vereinfachte Darstellung der Kommunikation
zwischen ioBroker, Gateway und Komponenten.

![Kommunikationsablauf](media/TradfriOverview_002.PNG)


### Installation des Adapters und Konfiguration der Instanz

<b>Schritt 1. Adapter installieren und Instanz erzeugen </b>

- Installieren des Adapters durch klicken auf ![Adapter](media/Adapter.PNG) in der linken Navigationsleiste des Webinterface
- in der nun erscheinenden Seite, in der Suche nach "Ikea Tradfri" suchen/filtern (siehe Abb. 01)
- den Adapter über das Icon ![Plus](media/plus.PNG) (letzte Spalte, ganz rechts) installieren. (hierbei wird auto. eine neue Instanz 
  des Adapters unter ![Instanzen](media/instanzen.PNG) angelegt)


![Ikea Tradfri Adapter hinzufügen](media/TradfriAdapterInstanz_002.PNG)

<b>Schritt 2. Übersicht der erzeugten Instanz und Konfiguration</b>

- Durch wechseln der Ansicht in der linken Navigationsleiste ![Instanzen](media/instanzen.PNG) werden die aktuell vorhandenen
  Instanzen angezeigt. Nach setzen des Filters auf "Tradfri" werden alle laufenden "Tradfri" Instanzen angezeigt. 
  Dies sollte der unteren Abbildung entsprechen.

![Ikea Tradfri Instanzansicht](media/TradfriAdapterInstanz_003optimiert.PNG)

- In der Spalte der jeweiligen Instanz bestehen folgende Anzeigen/ Aktionsmöglichkeiten Beschrieben von links nach rechts.
  - <b>Anzeige Aktivitätsstatus</b> (einfaches Ampelsystem)
    - ![Status Grün](media/status_green.PNG) ->Instanz läuft innerhalb der zu erwartenden Parameter, alles ok
    - ![Status Gelb](media/status_yellow.PNG) -> Instanz läuft, allerdings gibt es ggf. Probleme mit der Konfiguration des Tradfri Gateway
    - ![Status Rot](media/status_red.PNG) -> Instanz ist zwar gestartet, hat aber Probleme sich mit dem Host zu verbinden. 
  - <b>Aktionen</b>
    - ![Start Instanz](media/starting.PNG)Start und ![Stop Instanz](media/stop.PNG) Stop der Instanz ermöglichen diese Buttons
    - ![Start Instanz](media/konfiguration.PNG) Zugriff auf den Konfigurationsbereich der Instanz
    - ![Start Instanz](media/reload.PNG) Instanz wird neu gestartet 
    - ![Start Instanz](media/delete.PNG) Instanz wird unwiederruflich gelöscht

- <b>Adapterkonfiguration</b>
     - Über der Button ![Konfigurieren](media/konfiguration.PNG) zum Interface der "Adapterkonfiguration" wechseln. 
       Diese sollte in etwa der Abbildung (siehe unterhalb) entsprechen. Momentan beinhaltet diese zwei Tab-Reiter
       - <b>Einstellungen</b>
            - Unter Einstellungen befinden sich folgende Konfigurationsmöglichkeiten:
	      - <b>Gateway IP/Hostname</b> - Hostname ist "GW-", gefolgt von der MAC-Adresse ohne Sonderzeichen
                diese Information befindet sich auch auf der Rückseite des Tradfri Gateway selbst.
                (siehe Abb. Tradfri-Gateway Rückseite)
              - <b>Security-Code</b> - In deses Input Feld bite den Security-Code eintragen, 
                dieser befindet sich auf der Rückseite des Tradfri-Gateway (siehe Abb. Tradfri-Gateway Rückseite)
              - <b>Checkbox: "Übergangsdauer beibehalten"</b> - Standartmässig überschreibt der Gateway die Übergangsdauer jedes Mal 
                mit dem Standartwert 0,5 Sekunden. Wenn diese Checkbox aktiviert wurde, wird dieses Verhalten verhindert. 
              - <b>Nachkommastellen</b> - Das das Tradfri-Protokoll hat teilweise sehr eigenartige Schrittweiten für Zahlen, 
                   dieses Verhalten wird durch Runden auf die angegebenen Nachkommastellen hier verhindert.
       - <b>Virtuelle Gruppen</b>
	    - Zu allererst: Was sind Virtuelle Gruppen? Virtuelle Gruppen sind Gruppen in denen mehrere IoT-Geräte,
              aus dem Tradfri Sortiment unter einer Gruppe z.B. "Wohnzimmer" zusammengefasst werden können.






