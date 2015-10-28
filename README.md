# evohome-munin
Munin plugin for monitoring room/zone temperatures controlled by the Evohome of Honeywell


Plugin to show setpoint and measured temperature of zone.
Also show the outside temperature based on location

To make this plugin work make sure you install the following:

evohomeclient http://evohome-client.readthedocs.org/en/latest/
```
#pip install ./evohome-client
```

python-weather-api https://code.google.com/p/python-weather-api/
```
#pip install --allow-all-external  pywapi  --allow-unverified pywapi
```

ex: /etc/munin/plugin-conf.d/plugins
[evohome\*]
user root

To activate the plugin make a symlink

```
#ln -s /usr/local/share/munin/plugins/evohome_ /usr/local/etc/munin/plugins/evohome_Zonename
```

For the moment the zonenames should not contain spaces

Further set your username and password for the honeywell portal
For correct outside temperature lookup your location code at weather.com

