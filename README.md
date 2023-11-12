# ESPHOME-DOMOCHIP-WFP1

## Introduction

Several years ago, I purchased the [DOMOCHIP WFP1](https://github.com/Domochip/WirelessFilsPilotes) modules as part of a Kickstarter project to control my heaters over Wi-Fi. However, after some initial attempts, they ended up tucked away in a box, never integrated into my home automation setup.

This year, I stumbled upon the [Home Assistant](https://www.home-assistant.io) project and found myself eager to bring new features to my home. After successfully experimenting with various components, I decided to revisit the DOMOCHIP WFP1 module. However, I found its integration with Home Assistant to be quite complex. Given my love for coding microcontrollers like Arduino and ESP, I opted for a different approach - creating a new firmware using the fantastic [ESPHOME](https://esphome.io/index.html) tooling. To my surprise, I completed this task in just two days!

## About the Module

The WFP1 module utilizes an ESP8266, making it easy to work with and program. This module generates various signals to control heaters through the "pilot wire" in six different modes.

![The WFP1 module](https://github.com/cbijon/ESPHOME-DOMOCHIP-WFP1/blob/main/images/module.jpg)

You don't need to disassemble it; you can explore the [source code](https://github.com/Domochip/WirelessFilsPilotes/blob/master/src/WirelessFilsPilotes) to understand how it works. You can also check out my code. I didn't implement MQTT and OneWire setup since they were unnecessary for my requirements.

## Code Simulation

In my toolbox, I have some valuable tools to assist in this project. I use the [Wemos D1 mini](https://s.click.aliexpress.com/e/_d8l72oB), an inexpensive MCU that is very similar to the one inside the WFP1 module. This allows me to set up and test the code without risking the WFP1 module.

![Code Simulation](https://github.com/cbijon/ESPHOME-DOMOCHIP-WFP1/blob/main/images/simulation.jpg)

## How to Use It

To get started with ESPHOME, you can quickly set up the stack using Docker. Check the [documentation here](https://esphome.io/guides/getting_started_command_line.html). Once you've configured your YAML files with your home's specifics, such as your Wi-Fi credentials and the desired device name, compile it. This process will generate a firmware.bin file that you can download to your desktop.

Here's a little hack: rename the file as something like "WirelessFilsPilotes.v1.3.4-3.4.5.WFP1.bin" to bypass the security of the legacy Domochip firmware. This allows you to use their web interface directly to upload your new firmware.

After the upload, wait a few seconds, and Home Assistant will automatically discover your device. You now have a fully integrated device within Home Assistant!

![Home Assistant Integration](https://github.com/cbijon/ESPHOME-DOMOCHIP-WFP1/blob/main/images/homeassistant.png)

Enjoy the enhanced capabilities!

Feel free to adjust and expand this README as needed to provide more details or clarify any specific points.
