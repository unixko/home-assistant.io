---
title: EDL21
description: Instructions on how to integrate SML-based EDL21 smart meters into Home Assistant.
ha_category:
  - Sensor
ha_release: 0.107
ha_domain: edl21
ha_codeowners:
  - '@mtdcr'
---

The `edl21` integration lets you read German EDL21 smart meters using [SML](https://de.wikipedia.org/wiki/Smart_Message_Language) from Home Assistant.

In order to connect to the smart meter, an infrared transceiver is required.

Compatible transceivers:

- [DIY](https://wiki.volkszaehler.org/hardware/controllers/ir-schreib-lesekopf-rs232-ausgang)
- [Weidmann Elektronik Schreib-/Lesekopf USB](https://shop.weidmann-elektronik.de/index.php?page=product&info=24)

Tested smart meters:

- Iskraemeco MT175 (ISKRA MT175-D2A51-V22-K0t)

## Configuration

To set it up, add the following information to your `configuration.yaml` file:

```yaml
sensor:
  - platform: edl21
    serial_port: /dev/ttyUSB0
```

{% configuration %}
serial_port:
  description: The device to communicate with. When using ser2net, use socket://host:port.
  required: true
  type: string
{% endconfiguration %}
