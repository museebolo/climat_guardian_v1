# climat_guardian

Système de surveillance climatique

## Organisation

| dossier | description                                  |
|---------|----------------------------------------------|
| /doc    | Documentation                                |
| /sensor | Conteneur docker pour les capteurs (ESPHome) |
| /ha     | Conteneur docker Home Assistant              |

## Capteur de température et d'humidité

Le module ESP32 choisi est celui de LilyGo T5 v2.3.1. Il a un écran e-Paper.

[LilyGo T5 v2.3.1](https://www.lilygo.cc/products/t5-v2-3-1)

Exemples:

[LilyGo T5 Epaper](https://github.com/Xinyuan-LilyGO/LilyGo-T5-Epaper-Series)

Le capteur de température et d'humidité utilisé est un module AHT10. 
Celui-ci a besoin d'une alimentation (+3.3V et GND) et communique via un bus I2C (via les signaux SCL et SDA). 

[Capteur AHT10](doc/image/AHT10_IMG1.jpg)

[Capteur AHT10](doc/image/AHT10_IMG2.jpg)

Exemple pour ESPHome:

[Capteur AHT10](https://esphome.io/components/sensor/aht10.html)

Le câblage entre le LilyGo et le modue AHT10 est le suivant:

|ESP32  |AHT10|
|-------|-----|
| +3.3V | VIN |
| GND   | GND |
| 21    | SCL |
| 22    | SDA |

[LilyGo avec le câblage](doc/image/LILYGO_T5_BOT.jpg)

## Comment démarrer le contenur docker

Dans le dossier sensor:
  docker-compose up ou docker-compose up -d 

Dans le dossier ha:
  docker-compose up ou docker-compose up -d 
