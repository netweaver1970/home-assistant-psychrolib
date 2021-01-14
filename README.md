<dislcaimer> this is my first HomeAssistant component, as well as my first Python project, as well as my first (kind of) real github development. Yes, good luck on me...
The idea is to allow other people to use and/or enhance this component with extra functions/sensors to be used in HA for their own usage. 
I'm building further on the work of the home-assistant-dewpoint component, the reason I started this from scratch ( copy/paste/change) was because the original component name was too restrictive.
The method I'll use to incorporate extra functionality might not be the best or quickest but it's one that hopefully will work.
While building I might find out that I need to change things completely around.
This is my one of my side projects, so it gets time when I'm wanna try something new
  
Feel free to comment.

# home-assistant-psychrolib
HomeAssistant wrapper for Psychrometric calculations, provided by psychrolib

Home Assistant custom component to calculate multiple moist/dry air parameters, using temperature, humidity and pressure sensor(s).
Currently forseen
- dew point (the hopefully working base, the original idea)
- moist air density (my personal itch to scratch)

Installation
Use hacs with this repo URL https://github.com/netweaver1970/home-assistant-psychro or copy custom_components/ folder to your HA configuration.

Example configuration.yaml for dewpoint calculation
sensor:
  - platform: dewpoint
    sensors:
      dewpoint_outside:
        temperature: sensor.temperature_outside
        rel_hum: sensor.humidity_outside
      dewpoint_office:
        temperature: sensor.temperature_office
        rel_hum: sensor.humidity_office
      ...
[TODO] example for moist air density

[TODO] format + enhance following block
Configuration options
Key	Type	Required	Description
sensors	list	True	List of dewpoint sensors to generate.
Configuration options for sensors list
Key	Type	Required	Default	Description
friendly_name	string	False	sensor name	Custom name for the new sensor entity.
temperature	entity_id	True	none	Entity ID to read temperature from. (dry-bulb)
rel_hum	entity_id	True	none	Entity ID to read relative humidity from.
