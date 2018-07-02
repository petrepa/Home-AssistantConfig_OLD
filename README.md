# Home Assistant Configuration
This is how my Home Assistant configuration is set up. Hope this can be for inspiration for other users of the platform, as the many other repositories on GitHub has helped me on my home automation journey.

Be sure to :star2: the repo to follow along! Trying to update this regularly.

The setup is running on a Raspberry Pi 3 Model B, and as of this commit it is running on HASS version __0.66.1__.

This is how my default view looks, where I can controll the most important stuff. Am trying to only have the necessities on this view, and if I need anything more specific I can look to my other views.

__Note: The current screenshots do not replicate the latest configuration files!__
![default view](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/1_default_view.png)

Some screenshots of my other views.
![lights](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/2_lights.png)
![doors](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/3_doors.png)
![mediaplayers](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/4_mediaplayers.png)
![climate](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/5_climate.png)
![system](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/6_system.png)
![automations](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/7_automations.png)
![test](https://github.com/petrepa/Home-AssistantConfig/blob/master/screenshots/8_test.png)

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
  - Magnetic Door/Window Sensor
  - Mi Flora Sensor
  - Temperature and Humidity Sensor
  - Motion Sensor
- NetGear Router
- TP-Link HS100
- BroadLink
  - SP2
  - SP3
- Mill 900W Wifi electric heater (the Mill app sucks, so just using one of the smart plugs with it to controll it using the climate component in HASS)
- DIY projects - described below

## Services
- Tibber - Power provider which gives me real time electricity costs 

## Automations
* [Alarm Clock](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/alarm_clock.yaml)
  * Light - Night stand lamp turns gradually on when the alarm clock goes off
  * Sound - The Sonos Play:1 starts playing music when the alarm clock goes off
  * Blinds - The roller blinds goes up when the alarm clock goes off
* [Arriving Home](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/arriving_home.yaml)
  * Welcome - The Google Home welcomes me when I get home. This only happens if the door gets unlocked within five minutes from HA noticing im home. It also only triggers if Natalia is not home.
  * Door Actions - When I arrive home, I get a notification with buttons to open the front door and the apartment door, so I don't have to fiddle around in my pockets looking for my keys.
* [Audio](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/audio.yaml)
  * Night Mode - In the evening the Sonos Playbar in the living room turns the night mode on to suppress louder sounds. Turns back on in the mordning.
  * Welcome Home - A fun automation that is normally off. The idea is when Natalia gets home, the Google Home will welcome her as she walks in the door.
  * CO2 warning - If the CO2 level in our apartment gets to high, the Google Home will advice us to maybe open a window.
  * CO2 back to normal - When the CO2 is back to normal the Google Home tells us. This automation is normally turned off since we don t have any way to tell HASS if the windows already is closed. This can be fixed in the future by adding magnetic sensors to the window or something.
* [Away Mode](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/away_mode.yaml)
  * Away Mode - When nobody is at home the lights turns off, the heating lowers, the Sonos' stops playing, the TV turn off and I get a notification on my phone that Papki, our apartment, is in away mode.
* [Bathroom](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/bathroom.yaml)
  * Greeting - A fun automation made just to annoy Natalia a bit. When the door gets opened, you will be welcomed to the bathroom, so you can have a nice start while doing your important business.
  * Humidity warning - If the humidity level in our bathroom gets to high, probaby cause we are showring, the Play:1 in the bathroom will advice us to turn the fan on.
* [Bed](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/bed_button.yaml) - Our bed has a Xiaomi button mounted on it to controll our IKEA Trådfri bulbs on our nightstands in addition to a bed occupancy sensor.
  * Single Click - Toggle Natalia nightstand.
  * Double Click - Toggle Peter nightstand.
  * Long Press - Toggle the ceiling lamp.
  * Occupancy - When I get into bed the lights turn off, except the bedside, which turn into a night scene, and the Sonos ungroups any other room than the bedroom (often listen to music in the apartment before I go to bed).
* [Heating](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/heation.yaml) - This has lowered our electrical consumption quite a bit, since we live in an old house with bad isolation. 
  * Night time - The heat is lowered to 16 degrees celsius in the living room.
  * Day time - The heat is turned up to 22 degrees celsius in the living room.
  * Sombody came home - The heat is turned up to 22 degrees celsius in the living room and to 17 in the bedroom.
* [Charge iPad](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/ipad_notification.yaml) - Using an iPad Pro 10.5" to write my notes on when I study, so it is important that I have enough battery for the next school day.
  * Notification - Get a notification on my phone if my iPad has battery percentage under 45 22:00 o'clock.
* [Lights](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/lights.yaml)
   * Bedroom door opened, day time - The lights in the living room turn to the last state.
   * Bedroom door opened, night time - The lights in the living room turn to a night time scene, with warm and soft light to not interrupt our sleep if we have to get up for some reason during the night.
   * Disable Xiaomi Gateway Light - Since the Xiaomi Gateway light is so annoying and I did not find out how to disable it properly right away, I just made an automation to turn it off if it was turned on since we never use it.
* [Lock](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/lock.yaml)
  * Night - The door locks itself at night.
* [Plant](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/plant_alert.yaml)
  * Alert - I get an alert on my phone if the plants needs to be watered or fertilized. Plan to expand this in the future to prevent that our plants die.
* [TV](https://github.com/petrepa/Home-AssistantConfig/blob/master/automations/tv.yaml)
  * Movie - When there is a movie paying on the Chromecast, the light turns off. If the movie is paused or stopped, the light comes back on. This automation only triggers if the app name is 'Google Play Movies'. This is because we use the Chromecast throughout the day, and it would be really annoying if the lights turned off every time I was watching a YouTube video. When we watch movies we are 99% of the time watching it together and using Google Play.
  
## DIY Projects
* [MagicMirror](https://github.com/petrepa/MagicMirror)
* [Motorized roller blind](https://github.com/petrepa/rollerblind)
* [Apartment building door opener](https://github.com/petrepa/Dooropener)
* [Smart Table Fan](https://github.com/petrepa/MQTT-Table-Fan)
* [Bed occupancy sensor](https://wirres.net/article/articleview/10972/1/6/)
