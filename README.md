# PlantrHardwareComponent

this project includes everything that is needed to extract data from a garden and send it to a rest api for data collection

HARDWARE
- https://www.tinytronics.nl/shop/en/development-boards/microcontroller-boards/with-wi-fi/lilygo-ttgo-t-higrow-esp32-bme280-sensor
- https://www.tinytronics.nl/shop/en/development-boards/microcontroller-boards/with-wi-fi/lilygo-ttgo-t-higrow-esp32-dht11-sensor

COMPONENTS
- Lilly TTGO repository edited to spit out plant data every minute to a MQTT server (needs WIFI credentials in user-variables.h and optional plant name for ID purposes)
- Standard MQTT server defined in the docker-compose file
- Node-Red configured to subscribe to the MQTT gateway and spit the data as JSON to a defined adress
