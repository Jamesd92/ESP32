# ESP32 Modules

## WiFi

To install wifi onto a ESP the following Librarie is required.
Link: https://randomnerdtutorials.com/esp32-useful-wi-fi-functions-arduino/

The wifi module allows the ESP in three different modes.

1. AP (Access Point)
2. Station
3. Both

When the ESP32 is configured as an AP other devices can connect to it, the ESP32 acts as a router.

When the ESP32 is configured as a station it will connect to a router and communicate any other device on the network.

Module: #include <WiFi.h>

/_
Complete details at https://RandomNerdTutorials.com/esp32-useful-wi-fi-functions-arduino/
_/

#include <WiFi.h>

// Replace with your network credentials (STATION)
const char* ssid = "REPLACE_WITH_YOUR_SSID";
const char* password = "REPLACE_WITH_YOUR_PASSWORD";

void initWiFi() {
WiFi.mode(WIFI_STA);
WiFi.begin(ssid, password);
Serial.print("Connecting to WiFi ..");
while (WiFi.status() != WL_CONNECTED) {
Serial.print('.');
delay(1000);
}
Serial.println(WiFi.localIP());
}

void setup() {
Serial.begin(115200);
initWiFi();
Serial.print("RRSI: ");
Serial.println(WiFi.RSSI());
}

void loop() {
// put your main code here, to run repeatedly:
}

To Scan a network follow this link: https://github.com/espressif/arduino-esp32/blob/master/libraries/WiFi/examples/WiFiScan/WiFiScan.ino
