# HomeKit LED Strips using ESP8266

[Project Video Demo](https://youtu.be/LauEOlCBuvg)

My goal was to control individually addressable LED strips remotely in a convenient way.
I decided to use HomeKit, to leverage the Apple ecosystem and the Shortcut app.

HomeKit doesn't support individually addressable LED strips.
Instead, I first made the strip controllable as a simple lightbulb, with only one color for the entire strip.

I then tried to add some kind of drop-down menu to choose between different animation modes.
Unfortunately, I couldn't find any HomeKit device with such control. 
The best I came up with was to use a thermostat: change the temperature to change mode.
Every time the temperature is increased by 0.5, the next mode is set.

The LED animations used were taken from the DemoReel100.ino example from the FastLED library.

The [WiFiManager Library](https://github.com/tzapu/WiFiManager) was used to make setting up the WiFi connection easy, with a configuration portal.</br>
I used this [HomeKit Library](https://github.com/Mixiaoxiao/Arduino-HomeKit-ESP8266) to comunicate with HomeKit.</br>

Once everything was up and running, I created Shorcuts to easily switch between each mode by
turning off the lamp, and setting the temperature corresponding to the mode.

I can now control the light from the Home app, Shortcut, and with Siri.

Note: I had an issue where the first LED of the strip was randomly blinking. 
I downgraded to esp8266 2.7.4 (from Board Manager) to fix the issue.
(More info: https://github.com/FastLED/FastLED/issues/1260)
