# Start making TinyTuya
### Download the Tuya Smart or Smart Life application.
<!-- ![Smart Life](images/1.jpg) -->
### Add all available devices into the application
<!-- <img src="images/2.jpg" alt="drawing" style="width:200px;"/>
<img src="images/3.jpg" alt="drawing" style="width:200px;"/> -->

### Open Visual Studio Code and insert this code.

```python
import tinytuya

d = tinytuya.OutletDevice('DEVICE_ID_HERE', 'IP_ADDRESS_HERE', 'LOCAL_KEY_HERE')
d.set_version(3.3)
data = d.status() 
print('Device status: %r' % data)
```
### TinyTuya Installation
```
python -m pip install tinytuya
```
### TinyTuya Network Scanner
Scan for Address Device ID and Version for each device
```
python -m tinytuya scan
```

### Tuya Device Preparation
Controlling and monitoring Tuya devices on your network requires the following:

+ Address - Network address (IPv4) of the device e.g. 10.0.1.100
+ Device ID - Unique identifier for the Tuya device
+ Version - Tuya protocol version used (3.1, 3.2, 3.3, 3.4 or 3.5)
+ Local_Key - Security key needed to access the Tuya device.
_[How to create a Local Key account](https://drive.google.com/file/d/1vFOuHW5U2BTnTE89QYxYuNbrO_0VqXns/view?usp=sharing)_

### Run Setup Wizard
```
python -m tinytuya wizard
```
The wizard will ask you to enter your API Key , API Secret , API Region (cn, us, us-e, eu, eu-w). You can see it on the Overview page.
+ API Key: Access ID/Client ID
+ API Secret: Access Secret/Client Secret

The wizard creates a JSON file named device.json and contains all the device information, including name, id, and key. This list is: **_Local_Key_** of the device

Notes:
+ If you ever reset or re-pair your smart devices, the Local_Key will be reset and you will need to repeat the steps above.

### Turn devices on and off with TinyTuya
```python
import tinytuya

# Connect to Device
d = tinytuya.OutletDevice(
    dev_id='DEVICE_ID_HERE',
    address='IP_ADDRESS_HERE',      # Or set to 'Auto' to auto-discover IP address
    local_key='LOCAL_KEY_HERE', 
    version=3.3)

# Get Status
data = d.status() 
print('set_status() result %r' % data)

# Turn On
d.turn_on()

# Turn Off
d.turn_off()
```