# PlantrHardwareComponent

this project includes everything that is needed to extract data from a garden and send it to a rest api for data collection

HARDWARE
- https://www.tinytronics.nl/shop/en/development-boards/microcontroller-boards/with-wi-fi/lilygo-ttgo-t-higrow-esp32-bme280-sensor
- https://www.tinytronics.nl/shop/en/development-boards/microcontroller-boards/with-wi-fi/lilygo-ttgo-t-higrow-esp32-dht11-sensor

COMPONENTS
- Lilly TTGO repository edited to spit out plant data every minute to a MQTT server (needs WIFI credentials in user-variables.h and optional plant name for ID purposes)
- Standard MQTT server defined in the docker-compose file
- Node-Red configured to subscribe to the MQTT gateway and spit the data as JSON to a defined adress

OVERVIEW
How the compoments should talk (Note: the MQTT broker and NodeRed module should be hosten on a RPI or other hardware solution)

TTGO-ESP32>-------(mqtt messgae)-------->MQTT broker>-------(mqtt message)------>NodeRed>-----(REST API call)---->defined endpoint

HOW TO USE:

1: upload the TTGO hi-go microcontroller code (dont forget to add WiFi credentials and plant ID)
2: spin up the docker-compose.yaml. this activates the MQTT broker and nodeRed instance
3: observe the traffic on nodeRed, if needed the endpoint where data is sent can be changed. 
