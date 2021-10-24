# sp4ce-button
![The Button](https://i.imgur.com/3p3PEKL.png)

The Button is used to open the [B4CKSP4CE](https://0x08.in) door.

## Protocol

When the button is pressed or released, `down` or `up` (respectively) is published to the `bus/devices/opener.button/event` topic.

Pressing the button will also turn on green light for 1.5 seconds.

Publish `on` or `off` to the `bus/devices/opener.button/rainbow` topic to control rainbow effect.

## Hardware

The Button is powered with `DC 5V`.

3 addressable WS2812B LEDs are connected to `GPIO2`.

The button of the button is connected to `GPIO4`.

## Building and Flashing

### Secrets
Create and fill `secrets.yaml`:
```yaml
api_password: <string> # used to flash OTA
wifi_ssid: <string>
wifi_password: <string>
mqtt_broker: <string>
mqtt_username: <string>
mqtt_password: <string>
```

### Dependencies
You will need [esphome](https://esphome.io) to build the firmware.

```bash
pip3 install esphome
```

### Flashing
One simple command will build the firmware and flash the ESP8266.

```bash
esphome run sp4ce-button.yaml
```

The ESP8266 is flashed Over The Air by default. If you have a USB-UART adapter connected, you will be able to use it to flash over UART.

