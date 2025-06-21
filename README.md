# IKEA Air Quality Sensor
Converting and adding sensors to an off-the-shelf **VINDRIKTNING Air quality sensor**

- Turning it in to a Seven-in-One enviroment sensor 🏝
# Important Update:
In "Fix your IKEA Air Quality Temperature and Humidity readings" video, I made a mistake in moving (not duplicating) the following lines:
```yaml
    address: 0x76
    update_interval: 10s
```
This stops the first (orginal) set of Temperature and Humidity Sensors outputing data the C0²/VOC sensor (``platform: ccs811``) needs. 

# Fix for the Fix:
Copy back ``address: 0x76`` and ``update_interval: 10s`` to original set. I.E.:
```yaml
  ## Temp/Humidity/Pressure Sensor for CO²/VOC Sensor
  - platform: bme280_i2c
    temperature:
      id: bme_temp
      oversampling: 4x
    humidity:
      id: bme_humi
      oversampling: 4x
    address: 0x76
    update_interval: 10s
```
#### _Sensing List:_

> - 2.5μm Particle Count
> - Temperature / Humidiy / Pressure
> - CO² and VOC levels
> - Light Level (Basic)


#### ⚡*Code-y Bits*
- [V1 - Base ESPHome Code](https://github.com/3ative/IKEA-Air-Quality-Sensor/blob/main/ikea_aq_v1.yaml)
- [V2 - ESPHome Update](https://github.com/3ative/IKEA-Air-Quality-Sensor/blob/main/ikea_aq_v2.yaml)

Update to add a "Master" Switch to Enable/Disable sending speed control to the Ikea Air Filter
- [Automation Control](https://github.com/3ative/IKEA-Air-Quality-Sensor/blob/main/Automation_Master.yaml)




#### 🎬YouTube tutorials:
- [Part 1 - IKEA Air Quality ESPHome Convert](https://youtu.be/YmqtMTO5NVc)
- [Part 2 - IKEA Air Filter ESPHome Convert](https://youtu.be/WB4xxhgggHQ)
- [Part 3 - Automating the System](https://youtu.be/AnHLN7i5Fx4)

---
### 🤝 Found this useful, want to say 'Thanks' and support my efforts. CHEERS🍺
| Buy me a Coffee | PATREON |
|-----------------|---------|
| [![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-donate-yellow.svg?style=flat-square&logo=buy-me-a-coffee)](https://www.buymeacoffee.com/3ative) | [![Patreon](https://img.shields.io/badge/Patreon-support-red.svg?style=flat-square&logo=patreon)](https://www.patreon.com/3ative) |
---
