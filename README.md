# ESPHOME-DOMOCHIP-WFP1

## Intro

Somes years ago, i bought [DOMOCHIP WFP1](https://github.com/Domochip/WirelessFilsPilotes) modules from a kickstater project to drive my heaters on wifi. But after some try, i forget them in a box and they are never incorporated into my domotic setup. 

And this year i discovered the [Home Assistant](https://www.home-assistant.io) project, and i begin to want serioulsy something new at home. After some successfull tests with differents components, i decide to take a look another time on this module.

After find too complexe for the HA integration and  i am lover coding MCU  (Arduino and ESP). I decide to change my approach and rebuild a new firmware using the [ESPHOME](https://esphome.io/index.html) tooling (which was so cool). In 2 days, it was done !


## The beast :

The WFP1 module use an ESP8266. It's very generic and you can find this easly to code. This module generates differents signals to drive heater with six modes on "pilot wire".

![The WFP1 module](https://github.com/cbijon/ESPHOME-DOMOCHIP-WFP1/blob/main/images/module.jpg)

Ok, don't need to open it, we have [sources](https://github.com/Domochip/WirelessFilsPilotes/blob/master/src/WirelessFilsPilotes.cpp) ! We can learn everythings... You can see my code.

In fact i didn't implement MQTT and OneWire setup, useless for my requirement.

## Code simulation :

I have in my toolbox some cool stuff to help the new baby : [Wemos D1 mini](https://s.click.aliexpress.com/e/_d8l72oB) very cheap MCU et completly similar as the inside of WFP1 module. I can setup and test code without explode the WFP1 module.


![The WFP1 module](https://github.com/cbijon/ESPHOME-DOMOCHIP-WFP1/blob/main/images/simulation.jpg)


## Play it :

Setup the ESPHOME stack quickly with docker : [documentation there](https://esphome.io/guides/getting_started_command_line.html)

And put YAML files on it, confgure a little for your home, like WIFI creds and the name you want, compile it, generate a firmware.bin and download it on your desktop.

A little hack by renaming file as "WirelessFilsPilotes.v1.3.4-3.4.5.WFP1.bin" for example to bypass the security of the legacy domochip firmware and use there Web interface directly to upload your new firmware.

Well, after upload it, wait some seconds and Homeassistant will discover it automaticaly. Great, you have a new device completely integrated with Homeassistant !

Enjoy !


