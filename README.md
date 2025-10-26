# daikin-home-hub-modbus-home-assistant

# Daikin Home Hub Modbus Home Assistant Integration

## Purpose / Zweck

**English:**  
This project provides a Home Assistant custom integration for the Daikin Home Hub Modbus device. Its goal is to enable seamless monitoring and control of Daikin HVAC systems via Modbus protocol, allowing users to integrate their Daikin Home Hub with the Home Assistant platform for smart home automation.

**Deutsch:**  
Dieses Projekt stellt eine benutzerdefinierte Home Assistant-Integration für das Daikin Home Hub-Modbus-Gerät bereit. Ziel ist es, die Überwachung und Steuerung von Daikin-Klimasystemen über das Modbus-Protokoll zu ermöglichen, sodass Nutzer ihr Daikin Home Hub in die Home Assistant-Plattform für smarte Hausautomatisierung einbinden können.

## Features / Funktionen

**English:**  
- Communicate with Daikin Home Hub devices using Modbus protocol.
- Expose Daikin device data and controls as Home Assistant entities.
- Example configuration for easy setup.
- Open-source and extensible for community contributions.

**Deutsch:**  
- Kommunikation mit Daikin Home Hub-Geräten über das Modbus-Protokoll.
- Darstellung von Daikin-Gerätedaten und Steuerungen als Home Assistant-Entitäten.
- Beispielkonfiguration für einfachen Einstieg.
- Open Source und erweiterbar für Beiträge der Community.

## Usage / Verwendung

**English:**  
1. **Installation**
    - Copy the `custom_components/daikin_home_hub_modbus` directory into your Home Assistant `custom_components` folder.

2. **Configuration**
    - Add the integration to your `configuration.yaml`:
    ```yaml
    daikin_home_hub_modbus:
      host: 192.168.1.x
      port: 502
      # Add other Modbus and device options as required
    ```
    - Restart Home Assistant.

3. **Entities and Controls**
    - After setup, Daikin device data and controls will be available as Home Assistant entities.
    - You can automate, monitor, and control your HVAC system through the Home Assistant UI.

**Deutsch:**  
1. **Installation**
    - Kopiere das Verzeichnis `custom_components/daikin_home_hub_modbus` in deinen Home Assistant-Ordner `custom_components`.

2. **Konfiguration**
    - Füge die Integration zu deiner `configuration.yaml` hinzu:
    ```yaml
    daikin_home_hub_modbus:
      host: 192.168.1.x
      port: 502
      # Füge weitere Modbus- und Geräteoptionen nach Bedarf hinzu
    ```
    - Starte Home Assistant neu.

3. **Entitäten und Steuerungen**
    - Nach der Einrichtung sind Daikin-Gerätedaten und Steuerungen als Home Assistant-Entitäten verfügbar.
    - Du kannst dein Klimasystem über die Home Assistant-Oberfläche automatisieren, überwachen und steuern.
