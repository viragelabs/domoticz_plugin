# Virage Auto Discovery Plugin for Domoticz

A plugin to enable auto discovery of Virage Laboratories [light switches, dimmers and plugs](https://www.viragelabs.com/products/#hub) in Domoticz.

Thanks to [Erik Montnemery](https://github.com/emontnemery) for creating the initial version of this plugin.  Note that portions of the code have been modified to support Virage devices.

## Installation

Note that a functioning MQTT Broker must be present on your network for this plugin to work.  It is possible to install [Mosquitto](https://mosquitto.org/) on the same device as Domoticz.  If you are using a [VirageHub](https://www.viragelabs.com/products/#hub), or a Raspberry Pi 4-based installation with minimum 32GB SSD, you can use the Virage Domoticz image which comes pre-configured with Mosquitto and Avahi to help Virage devices automatically find it.

Copy the plugin.py file into the Domoticz /plugins/virage_mqtt_discovery/ folder.  The location of this folder can vary depending on your method of installation and platform.  For Raspberry Pi OS, it defaults to /home/[username]/domoticz/plugins.

Restart your Domoticz instance.

Go to the Setup menu, then Hardware, and create a new entry of the type MQTT discovery.

*Note that the plugin currently only works with systems using Python 3.8X or below.  If you system does not meet these requirements, it may hang when rebooting.  If this is the case, simply remove the plugin and your system should boot normally.*

Enter a Name, the MQTT Server Address, Username, and Password for your MQTT Broker.  Leave the other fields at their default settings.

Click Add, and you will be prompted to look in the Devices area (under Setup) for discovered devices.

The MQTT Discovery function of Domoticz will automatically find and configure the VirageSwitch, VirageDimmer, and ViragePlug, and the controls for these devices, once discovered, can be found in the Switches tab.

To set up a VirageBridge, you need to use the MQTT Client Gateway with LAN interface (see instructions on the Virage website).
