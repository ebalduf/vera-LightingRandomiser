vera-LightingRandomiser
=======================

Simulates lighting activity in an occupied house

## Configuration

### Zones file

Copy `L_LightingRandomiser_zones.sample.lua` to `L_LightingRandomiser_zones.lua`.

Adjust the file as required for your network. The numeric keys within each zone
are the Device IDs that you want to control. Supported `types` are "dimmer" and
"switch". For dimmer add a `percentage` integer of between 1 and 100.

### Schedule file

Copy `L_LightingRandomiser_schedule.sample.lua` to
`L_LightingRandomiser_schedule.lua`.

Adjust the file as required for your network. Each `zone` must relate to a key
in your `L_LightingRandomiser_zones.json` file. Then set min and max On and Off
times. These times must be in one of 3 formats
* `hh:mm:ss` format.
* The sunrise/sunset keywords
* A delta time. Identify the value a as delta time be prefixing with + or -.
  To help with clarity use - in the min and + in the max (it ignores the + or -)

Be sure that your `minOff` time is greater than your `maxOn` time.

## Installation

Copy the following files to Vera using the Apps > Develop Apps > Luup files tool.

* D_LightingRandomiser.xml
* I_LightingRandomiser.xml
* L_LightingRandomiser.lua
* L_LightingRandomiser_zones.lua
* L_LightingRandomiser_schedule.lua
* json.lua

Now manually create a new device with a `Upnp Device Filename` of "D_LightingRandomiser.xml".

To cancel the schedule, delete the device.

Enjoy!
