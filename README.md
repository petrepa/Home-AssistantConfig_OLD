# Home Assistant Configuration
This is how my Home Assistant configuration is set up. Hope this can be for inspiration for other users of the platform, as the many other repositories on GitHub has helped me on my home automation journey.

The setup is running on a Raspberry Pi 3 Model B, and as of this commit it is runing on HA version __0.66.1__.

This is how my default view looks, where I can controll the most important stuff.
![default view](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/1_default_view.png)

Some screenshots of my other views.
![lights](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/2_lights.png)
![doors](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/3_doors.png)
![sonos](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/4_sonos.png)
![cast](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/5_cast.png)
![system](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/6_system.png)
![test](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/7_test.png)

## Devices

- Google Chromecast 2nd generation
- Google Home
- Philips Hue Bridge
  - Philips Hue Lightstrip Plus
  - Philips Hue Colour Bulbs
  - Ikea Trådfri (connected to the Hue system)
- Nest Protect
- Netatmo Weather Station
- Sonos
  - Sonos Playbar
  - Sonos Play:1
  - Sonos Connect
- Samsung UE49KS7005
- Sesame Smart Lock
- Xiaomi Smart Home Gateway
  - Xiaomi Magnetic Door/Window Sensor
  - Xiaomi Mi Flora Sensor
  - Xiaomi Temperature and Humidity Sensor
- NetGear Router
- TP-Link HS100
- BroadLink SP2
- Mill 900W Wifi electric heater (the Mill app sucks, so just using one of the smart plugs with it to controll it using the climate component in HA)
- MagicMirror
- Various DIY projects using ESP8266

## Automations
* [Alarm Clock](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/alarm_clock.yaml)
  * Light - Night stand lamp turns gradually on when the alarm clock goes off
  * Sound - The Sonos Play:1 starts playing music when the alarm clock goes off
  * Blinds - The roller blinds goes up when the alarm clock goes off
* [Audio](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/audio.yaml)
  * Night Mode - In the evening the Sonos Playbar in the living room turnes the night mode on to suppress louder sounds
  * Welcome Home - A fun automation that is normally off. The idea is when Natalia gets home, the Google Home will welcome her as she walks in the door
* [Away Mode](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/away_mode.yaml)
  * Away Mode - When nobody is at home the lights turn off, the heating lowers, the Sonos' stops playing, the TV turn off and I get a nitification on my phone that Papki, our apartment, is in away mode
* [Bathroom](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/bathroom.yaml)
  * Greeting - A fun automation made just to annoy Natalia a bit. When the door gets opened, you will be welcomed to the bathroom, so you can have a nice start doing your important business
* [Bed Button](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/bed_button.yaml) - Our bed has a Xiaomi button mounted on it to controll our IKEA Trådfri bulbs on our nightstands
  * Single Click - Toggle Natalia nightstand
  * Double Click - Toggle Peter nightstand
  * Long Press - Toggle the ceiling lamp
* [Heating](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/heation.yaml) - This has lowered our electrical consumption quite a bit, since we live in an old house with bad isolation. 
  * Night time - The heat is lowered to 16 degrees celsius in the living room
  * Day time - The heat is turned up to 22 degrees celsius in the living room
  * Sombody came home - The heat is turned up to 22 degrees celsius in the living room and to 17 in the bedroom
* [Charge iPad](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/ipad_notification.yaml) - Using an iPad Pro 10.5" to write my notes on when I study, so it is important that I have enough battery for the next school day.
  * Notification - Get a notification on my phone if my iPad has battery percentage under 45 22:00 o'clock.
* [Lights](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/lights.yaml)
   * Bedroom door opened, day time - The lights in the living room turn to the last state
   * Bedroom door opened, night time - The lights in the living room turn to a night time scene, with warm and soft light to not interrupt our sleep if we have to get up for some reason during the night.
* [Lock](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/lock.yaml)
  * Night - The door locks itself at night
* [Plant](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/plant_alert.yaml)
  * Alert - I get an alert on my phone it the big plant needs to be watered. Plan to expand this in the future to prevent that our plants die
  
