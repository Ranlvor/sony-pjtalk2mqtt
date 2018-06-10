This module was cloned from https://github.com/Galala7/pySDCP and modified slightly for the MQTT-bridge


 # pySDCP
Sony SDCP / PJ Talk projector control 

Python **3** library to query and control Sony Projectors using SDCP (PJ Talk) protocol  over IP.

##Features:
* Autodiscover projector using SDAP (Simple Display Advertisement Protocol)
* Query and change power status
* Toggle input between HDMI-1 and HDMI-2

## More features
The SDCP protocol allow to control practically everything in projector, i.e. resolution, brightness, 3d format...
If you need to use more commands, just add to _protocol.py_, and send with _my_projector._send_command__

### Protocl Documnetation:
* [Link](https://www.digis.ru/upload/iblock/f5a/VPL-VW320,%20VW520_ProtocolManual.pdf)
* [Link](https://docs.sony.com/release//VW100_protocol.pdf)


#Supported Projectors
Supported Sony projectors should include:
* VPL-VW515
* VPL-VW520
* VPL-VW528
* VPL-VW665
* VPL-VW315
* VPL-VW320
* VPL-VW328
* VPL-VW365
* VPL-VW100
* VPL-HW65ES

## Installation 
```pip install pySDCP```

## Examples


Sending any command will initiate autodiscovery of projector if none is known and will cary on the command. so just go for it and maybe you get lucky:
```
import pySDCP

my_projector = pySDCP.Projector()

my_projector.get_power()
my_projector.set_power(True)
```

Skip discovery to save time or if you know the IP of the projector
```
my_known_projector = pySDCP.Projector('10.1.2.3')
my_known_projector.set_HDMI_input(2)
```

# Credits
This plugin is based on [sony-sdcp-com](https://github.com/vokkim/sony-sdcp-com) NodeJS library by [vokkim](https://github.com/vokkim).

## See also
 [homebridge-sony-sdcp](https://github.com/Galala7/homebridge-sony-sdcp) Homebridge plugin to control Sony Projectors.
 
