# evohome-munin
Munin plugin for monitoring room/zone temperatures controlled by the Evohome of Honeywell


Plugin to show setpoint and measured temperature of zone.
Also show the outside temperature based on location

To make this plugin work make sure you install the following:

evohomeclient http://evohome-client.readthedocs.org/en/latest/
```
pip install ./evohome-client
```

python-munin framework
http://samuelks.com/python-munin/


python-weather-api https://code.google.com/p/python-weather-api/
```
pip install --allow-all-external  pywapi  --allow-unverified pywapi
```
If this doesn't work use the manual install:
```
wget https://launchpad.net/python-weather-api/trunk/0.3.8/+download/pywapi-0.3.8.tar.gz
tar xzvf pywapi-0.3.8.tar.gz
cd  pywapi-0.3.8
python setup.py build
python setup.py install
```

Find your plugins directory, this is depended on your OS
ex: /etc/munin/plugin-conf.d/plugins

[evohome\*]
user root

To activate the plugin make a symlink:
```
ln -s /usr/local/share/munin/plugins/evohome_ /usr/local/etc/munin/plugins/evohome_Zonename
```
Notice, this symlink is depended on your system/OS
For example some system it should be:
```
ln -s /usr/share/munin/plugins/evohome_ /etc/munin/plugins/evohome_Zonename
```

For the moment the zonenames should not contain spaces

Further set your username and password for the honeywell portal
For correct outside temperature lookup your location code at http://weather.com

# Example #
![example munin](https://raw.githubusercontent.com/Infern1/evohome-munin/master/example_evohome_temperature.png)
