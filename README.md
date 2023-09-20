# Start making TinyTuya
## 1.Download the Tuya Smart or Smart Life application.
<!-- ![Smart Life](images/1.jpg) -->
## 2.Add all available devices into the application
<!-- ![Smart Life](images/2.jpg)
![Smart Life](images/3.jpg) -->
<img src="images/3.jpg" alt="drawing" style="width:200px;"/>
## 3.Open Visual Studio Code and insert this code.

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

### Tuya Device Preparation
Controlling and monitoring Tuya devices on your network requires the following:

+ Address - Network address (IPv4) of the device e.g. 10.0.1.100
+ Device ID - Unique identifier for the Tuya device
+ Version - Tuya protocol version used (3.1, 3.2, 3.3, 3.4 or 3.5)
+ Local_Key - Security key needed to access the Tuya device.
_[How to create a Local Key account](https://drive.google.com/file/d/1vFOuHW5U2BTnTE89QYxYuNbrO_0VqXns/view?usp=sharing)_
