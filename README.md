# myWebServerAsync
myWebServerAsync library for ESP8266/NodeMCU Arduino IDE.  

This is a redesign of of project:  https://github.com/nailbuster/myWebServerAsync

Changes from the original:

1) Authentication now works.
2) 'request->arg(0) bug fixed.
3) JSON load/save is now handled through the html body instead of being passed as url arguments.
4) Embedded "wifisetup.html" was changed to support new JSON methods.

This server uses the Async WEB/TCP library so that it can handle requests quickly and non-blocking.  It also includes jquery/bootstrap/css/fontawesome within the library so they are available when booted up.

You can try and flash the bin file to your esp8266 to sample the webserver....

Uses Arduino IDE,  ensure latest esp8266 from:  https://github.com/esp8266/Arduino  

Library requires the use of the following 3rd party libraries to be installed:

Async Web Server https://github.com/me-no-dev/ESPAsyncWebServer

Async TCP Library https://github.com/me-no-dev/ESPAsyncTCP

TimeLib for ntp here:  https://github.com/PaulStoffregen/Time

Arduino Json here:  https://github.com/bblanchon/ArduinoJson
NOTE: Must use ArduinoJson version 5.13.5 train as version 6+ does not work with this library.

This library is an easy starting/base for working on the esp8266...  myWebServer will serve files from the SPIFFs on your device.  You should only use this on devices with available spiffs!  (4MB on nodemcu for example).

FEATURES:  

It will try and connect to your AccessPoint, if not configed or able toconnect it will auto-start local AP like "myespxxxx".  You just connect to that AP with your phone/tablet and it will display Wifi connect configuration.  (Uses captive DNS so you can just go to browser and type setup.com or "anything".com).
If captive DNS does not work browse to http://192.168.4.1

Restart nodemcu after you've configured connection....

Once device connected to your local router/internet.  You go to it's local lan IP, or if your system supports mDNS you can type http://"device_name.local" on your browser. (Device name was configured in during WiFi setup)  
Virgin configs will bring up an integrated HTML file browser.  You can upload multiple files or drag files to top to allow you webserver to work...(index.html...etc).

Supports OTA updating of ESP device via Wifi.

NTP time support to grab current date/time.
