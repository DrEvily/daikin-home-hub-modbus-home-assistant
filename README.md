# daikin-home-hub-modbus-home-assistant
This project provides a Home Assistant custom integration for the Daikin Home Hub Modbus device. Its goal is to enable seamless monitoring and control of Daikin HVAC systems via Modbus protocol, allowing users to integrate their Daikin Home Hub with the Home Assistant platform for smart home automation.

# Daikin Home Hub Modbus Home Assistant Integration

## Purpose

This project provides a Home Assistant custom integration for the Daikin Home Hub Modbus device. Its goal is to enable seamless monitoring and control of Daikin HVAC systems via Modbus protocol, allowing users to integrate their Daikin Home Hub with the Home Assistant platform for smart home automation.

## Features

- Communicate with Daikin Home Hub devices using Modbus protocol.
- Expose Daikin device data and controls as Home Assistant entities.
- Example configuration for easy setup.
- Open-source and extensible for community contributions.

## Usage

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

## Contributing

Issues and pull requests are welcome! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License.
