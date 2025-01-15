# Home Assistant Zigbee2MQTT Edge Setup Guide

## 1 Prerequisites

- **Home Assistant**: You need a Home Assistant OS or Supervised version. (On other versions, the [add-ons feature may not be available](https://www.home-assistant.io/installation/#advanced-installation-methods), so you won't be able to install the Zigbee2MQTT addon.)

- **Zigbee USB adapter**: You need a Zigbee USB adapter. (If you don't have one, you can purchase one from the market.)

## 2 Install MQTT broker on Home Assistant

If you don't have an MQTT broker yet; in Home Assistant go to Settings → Add-ons → Add-on store and install the Mosquitto broker add-on, then start it.

<img src="img/install-mosquitto-broker.gif" width="400" alt="Install Mosquitto broker">

## 3 Install Zigbee2MQTT Edge for Home Assistant

Click the Add repository button below to add the Zigbee2MQTT repository:

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fzigbee2mqtt%2Fhassio-zigbee2mqtt)

(You might need to enter the internal IP address of your Home Assistant instance first)
<img src="img/ha-internal-ip.png" width="400" alt="Home Assistant internal IP">

Click Add → Close

<img src="img/add-repository.png" width="400" alt="Add repository">

In the add-on store, you'll see two versions of Zigbee2MQTT:

- **Zigbee2MQTT**: The stable release (recommended for most users)
- **Zigbee2MQTT Edge**: Tracks the `dev` branch with latest features and fixes

Select "Zigbee2MQTT Edge" and click Install. Wait until the installation completes.

> **Note**: Zigbee2MQTT Edge tracks the dev branch of Zigbee2MQTT, providing access to the latest features and fixes before they are officially released. While this version offers cutting-edge functionality, it may be less stable than the regular release.

<img src="img/install-zigbee2mqtt-edge.png" width="400" alt="Install Zigbee2MQTT Edge">

## 4 Configure Zigbee2MQTT Edge

### 4.1 MQTT Configuration

If you're using the Mosquitto broker add-on, set the MQTT server configuration:

```yaml
server: mqtt://localhost:1883
```

<img src="img/mqtt-server-config.png" width="400" alt="MQTT server configuration">

### 4.2 USB Adapter Configuration

Find your Zigbee USB adapter path in Home Assistant:
Go to Settings → System → Hardware → All Hardware

<img src="img/find-usb-adapter-path.gif" width="400" alt="Find USB adapter path">

Configure the adapter settings (example using `/dev/ttyACM0`):

```yaml
adapter: zstack
port: /dev/ttyACM0
```

<img src="img/configure-adapter-settings.png" width="400" alt="Configure adapter settings">

Start the Zigbee2MQTT Edge add-on

<img src="img/start-zigbee2mqtt.png" width="400" alt="Start Zigbee2MQTT">

## 5 Join device to Zigbee2MQTT

After the Zigbee2MQTT Edge add-on is started, you can join devices through the web interface:

<img src="img/join-devices-interface.png" width="400" alt="Join devices interface">

## 6 Troubleshooting

If the add-on fails to start with a "USB adapter discovery error", you'll need to manually specify the correct port:

- Try `/dev/ttyUSB0` or `/dev/ttyAMA0` if you have only one USB device connected
- Use the Home Assistant CLI command `ha hardware info` to identify the correct port

## 7 Read More

- [Zigbee2MQTT Hassio Addon](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt?tab=readme-ov-file#installation)
- [Install Zigbee2MQTT, Setup in 10 Minutes - YouTube](https://www.youtube.com/watch?v=sfsZF0R0HtE)
