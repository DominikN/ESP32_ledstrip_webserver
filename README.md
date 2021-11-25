# ESP32_ledstrip_webserver
*Control WS2812 based LED strip using a web server hosted by ESP32.*

**1. Flashing ESP32**

Clone the repo and open it using [Visual Studio Code](https://code.visualstudio.com/) with [PlatformIO extension](https://platformio.org/install/ide?install=vscode) installed.


**2. Get Husarnet join code**

- Register at https://app.husarnet.com/
- Click **Create network** button, name it (eg. `mynet`), and click **Create** button
- Click **Add element** button and go to the `join code` tab
- Copy your join code (looking like `fc94:b01d:1803:8dd8:b293:5c7d:7639:932a/xxxxxxxxxxxxxxxxxxxxxxxxx`) place that join code in this line of `*.ino` file:

```cpp
const char* husarnetJoinCode = "xxxxxxxxxxxxxxxxxxxxxx";
```

Now build and flash ESP32:

```bash
# Build project
$ pio run

# Upload firmware
$ pio run --target upload
```

**3. Connect over the internet to a webpage hosted by ESP32**

Connect your laptop (from which you will access the LED strip over the Internet) to the same Husarnet network. Installation methods and available platforms are listed here: https://husarnet.com/docs/ 

Open a web browser and write an address to your ESP32 with 8000 port, eg `http://ledstrip:8000`


