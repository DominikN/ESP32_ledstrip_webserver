# ESP32_ledstrip_webserver
*Control WS2812 based LED strip using a web server hosted by ESP32.*

**1. Install NeoPixelBus library in Arduino IDE:**
* open "Tools" -> "Manage Libraries"
* search for "NeoPixelBus by Makuna"
* click "Install" button

**2. Install Husarnet IDF for ESP32:**
* open "File" -> "Preferences"
* in a field "Additional Board Manager URLs" add this link: https://files.husarion.com/arduino/package_esp32_index.json

**3. Select ESP32 dev board:**
* open "Tools" -> "Board"
* select "ESP32 Dev Module" under "ESP32 Arduino (Husarnet)" section

**4. Run demo:**
* Open ESP32_ledstrip_webserver.ino
* modify line 9 to setup number of pixels in your LED strip
* modify lines 22 - 33 to add your Wi-Fi network credentials
* connect input data pin of your LED strip to "G12" pin of your ESP32 dev board
* upload project to your ESP32 board 
* In Arduino IDE open "Tools" -> "Serial Monitor" and wait until your ESP32 is connected to Wi-Fi network. After a few seconds you should see a similar link to this: ```[10009675] Visit https://app.husarnet.com/husarnet/fc94f91f5992989f83474cc8abf7329bf8ae7f3ee4a9xxxxyyyyzzzz to configure the device``` . Copy that link and open in your web browser
* Name your device (eg. ledstrip), click "Add to network" and select "Create new network" - and also name it (eg. ledstripnet)
* open "ledstripnet" and left click "ledstrip" element
* select "Make the Web UI public" and click update
* in the "Info" column withing "ledstripnet" network you should see "Web UI" button with a public available link to a control panel. Each time you will power your ESP32 board under that link you will have an access to a web UI to control your LED strip

**5. (optional) Improvements - if you don't want to have any public available link to your ESP32 you will need to add your laptop to the "ledstripnet" network:**
* install Husarnet on your Linux device (https://docs.husarnet.com/getting-started/ ) and add that to your network
* on your Linux device open a web browser and write an address to your ESP32 with 8000 port, eg `http://ledstrip:8000`


