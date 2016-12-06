# evohome-munin
Munin plugin for monitoring room/zone temperatures controlled by the Evohome of Honeywell


Plugin to show setpoint and measured temperature of zone.
Also show the outside temperature based on location

To make this plugin work make sure you install the following:

## evohome-client
evohomeclient http://evohome-client.readthedocs.org/en/latest/
```
pip install evohomeclient
```


## python-munin framework
http://samuelks.com/python-munin/
```
wget https://github.com/samuel/python-munin/archive/master.zip
unzip master.zip
cd python-munin-master/
python setup.py build
python setup.py install
```


## python-weather-api 

https://code.google.com/p/python-weather-api/
(using a new fork from github)
```
wget https://github.com/danbraun/pywapi/archive/master.zip -O pywapi.zip
unzip pywapi.zip
cd pywapi-master
python setup.py build
python setup.py install
```
If this doesn't work use the manual install:
```
wget https://launchpad.net/python-weather-api/trunk/0.3.8/+download/pywapi-0.3.8.tar.gz
tar xzvf pywapi-0.3.8.tar.gz
cd  pywapi-0.3.8
python setup.py build
python setup.py install
```

## Munin setup 

Find your plugins directory, this is depended on your OS
ex: /etc/munin/plugin-conf.d/plugins
and place the following there:
```
[evohome*]
user root
```

Download https://github.com/Infern1/evohome-munin/blob/master/evohome_


and place it in your munin plugin folder eg.
```
wget https://raw.githubusercontent.com/Infern1/evohome-munin/master/evohome_
/usr/local/share/munin/plugins/
or
/etc/munin/plugins
```

To activate the plugin make a symlink:
```
ln -s /usr/local/share/munin/plugins/evohome_ /usr/local/etc/munin/plugins/evohome_Zonename
```
Notice, this symlink is depended on your system/OS
For example some system it should be:
```
ln -s /usr/share/munin/plugins/evohome_ /etc/munin/plugins/evohome_Zonename
```

**For zone names containing spaces, replace the spaces with underscores in the symlink name**

Zone names are case sensitive and must match the case entered on the Evotouch controller

Further set your username and password for the honeywell portal in the file evohome_

For correct outside temperature lookup your location code at http://weather.com
```
    username = 'user@mail.com' 
    password = 'yoursecretpassword'
    location = 'NLXX0010'  
```



# Example #
![example munin](https://raw.githubusercontent.com/Infern1/evohome-munin/master/example_evohome_temperature.png)
