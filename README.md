# Daikin Home Hub Modbus Home Assistant Integration

## Purpose / Zweck

**English:**  
This project provides a Home Assistant custom integration for the Daikin Home Hub EKRHH Modbus device. Its goal is to enable seamless monitoring and control of Daikin HVAC systems Altherma 3 R H MT M via Modbus protocol, allowing users to integrate their Daikin Home Hub with the Home Assistant platform for smart home automation. Home Hub is connected to Network with RJ45 cable. Fixed IP is recommended.

**Deutsch:**  
Dieses Projekt stellt eine benutzerdefinierte Home Assistant-Integration für das Daikin Home Hub-Modbus-Gerät EKRHH bereit. Ziel ist es, die Überwachung und Steuerung von Daikin-Klimasystemen Altherma 3 R H MT M über das Modbus-Protokoll zu ermöglichen, sodass Nutzer ihr Daikin Home Hub in die Home Assistant-Plattform für smarte Hausautomatisierung einbinden können. Der Home Hub wird dabei in das Heim-Netzwerk per RJ45 Kabel eingebunden. Es empfiehlt sich eine statische IP zu setzen.

## Features / Funktionen

**English:**  
- Communicate with Daikin Home Hub EKRHH devices using Modbus protocol.
- Expose Daikin device data and controls as Home Assistant entities.
- Example configuration for easy setup.
- Open-source and extensible for community contributions.
- Tested for Daikin Altherma 3 R MT (MMI 7.8.0) with Home Hub (Firmware 2.4.3)

**Deutsch:**  
- Kommunikation mit Daikin Home Hub-Gerät EKRHH über das Modbus-Protokoll.
- Darstellung von Daikin-Gerätedaten und Steuerungen als Home Assistant-Entitäten.
- Beispielkonfiguration für einfachen Einstieg.
- Open Source und erweiterbar für Beiträge der Community.
- Gestestet mit einer Daikin Altherma 3 R MT (MMI 7.8.0) und Home Hub (Firmware 2.4.3)

## Usage / Verwendung

**English:**  
1. **Installation**
    - Copy the `packages` directory into your Home Assistant `config` folder.

2. **Configuration**
    - Add the integration to your `configuration.yaml`:
    ```yaml
    homeassistant:
    packages: !include_dir_merge_named packages/
    ```
    - check that file "daikin.yaml" is given in subfolder packages/modbus/
    - Add the integration to your `secrets.yaml` and edit ip address (port & slave usually fits):
    ```yaml
    daikin_modbus_host_ip: 192.xxx.xxx.xxx # TODO update with the IP of your homehub. No default. Check your router.
    daikin_modbus_port: 502 # TODO update with the Modbus port of your homehub. Default is '502'
    daikin_modbus_slave: 1 #TODO update with the slave address of your homehub. Default is '1'
    ```
    - Restart Home Assistant.

3. **Entities and Controls**
    - After setup, Daikin device data and controls will be available as Home Assistant entities.
    - You can automate, monitor, and control your HVAC system through the Home Assistant UI.
    - You can use the dashboard from `dashboards` as a starting point.

**Deutsch:**  
1. **Installation**
    - Kopiere das Verzeichnis `packages` in deinen Home Assistant-Ordner `config`.

2. **Konfiguration**
    - Füge die Integration zu deiner `configuration.yaml` hinzu:
    ```yaml
    homeassistant:
    packages: !include_dir_merge_named packages/
    ```
    - pürfe ob sich die Datei "daikin.yaml" im Unterordner packages/modbus/ befindet
    - Füge in der `secrets.yaml` die IP Adresse des Home Hubs zu (port & slave optional anpassen):
    ```yaml
    daikin_modbus_host_ip: 192.xxx.xxx.xxx # TODO update with the IP of your homehub. No default. Check your router.
    daikin_modbus_port: 502 # TODO update with the Modbus port of your homehub. Default is '502'
    daikin_modbus_slave: 1 #TODO update with the slave address of your homehub. Default is '1'
    ```
    - Starte Home Assistant neu.

3. **Entitäten und Steuerungen**
    - Nach der Einrichtung sind Daikin-Gerätedaten und Steuerungen als Home Assistant-Entitäten verfügbar.
    - Du kannst dein Klimasystem über die Home Assistant-Oberfläche automatisieren, überwachen und steuern.
    - Du kannst das Dashboard unter `dashboards` verwenden.

## Known  Issues

**English:**  
    - Temperatures are sent via Modbus with different scaling in the holding and input registers. This seems very cumbersome and complicated, and is not explained or described in the documentation. Ultimately, this means that Modbus participants have to implement different scaling. The standard Home Assistant Thermostat Widget cannot do this. A change is desirable and has been sent to support.
    - Temperature values are only sent/handled as integers in the protocol. This means that although you can select 23.5 degrees as the target temperature in the thermostat, only 23 degrees is actually sent to the Altherma. 

**Deutsch:**
    - Die Temperaturen werden im Holding- und im Input Register unterschiedlich skaliert per Modbus versendet. Dies erscheint sehr umständlich und kompliziert, wird in der Dokumentation auch nicht begründet/ beschrieben. Letztlich führt es dazu, dass Modbus Teilnehmer unterschiedliche Skalierungen implementieren müssen. Das Standard Home Assistant Thermostat Widget kann dies nicht. Eine Änderung ist wünschenswert und wurde an den Support gesendet.
    - Temperaturwerte werden im Protokoll nur ganzzahlig versendet/ gehandhabt. Dies führt dazu, dass man zwar 23.5 Grad im Thermostat als Solltemperatur wählen kann, aber tatsächlich dann nur 23Grad an die Altherma gesendet werden. 
