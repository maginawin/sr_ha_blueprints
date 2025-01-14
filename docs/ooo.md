# Join device to Home Assistant through Zigbee2MQTT Edge Addon

## Prerequisites

- **Home Assistant**: You should prepare a Home Assistant OS version or Supervised version. (In other version, the [add-ons feature may not be available](https://www.home-assistant.io/installation/#advanced-installation-methods), so you can't install Zigbee2MQTT addon.)
- **Zigbee USB adapter**: You should prepare a Zigbee USB adapter. (If you don't have one, you can buy one from the market.)

## Install MQTT broker on Home Assistant

If you don't have an MQTT broker yet; in Home Assistant go to Settings → Add-ons → Add-on store and install the Mosquitto broker add-on, then start it.

## Install Zigbee2MQTT for Home Assistant

Click the Add repository button below.

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fzigbee2mqtt%2Fhassio-zigbee2mqtt)

(You might need to enter the internal IP address of your Home Assistant instance first)
![alt text](<CleanShot 2025-01-14 at 17.29.41@2x.png>)

click Add → Close

![alt text](<CleanShot 2025-01-14 at 17.31.45@2x.png>)

## Join device to Zigbee2MQTT

## Read More

- [Zigbee2MQTT Hassio Addon](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt?tab=readme-ov-file#installation)
- [Install Zigbee2MQTT, Setup in 10 Minutes - YouTube](https://www.youtube.com/watch?v=sfsZF0R0HtE)
