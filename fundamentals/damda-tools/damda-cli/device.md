# Device

Commands to retrieve device information and a list of components installed in the device

## get-device

* Retrieves information of a specific device.
* Either --device-id or --device-alias is required
  * **However --device-alias is not yet supported.**

### command

```
$ damda get-device [OPTIONS]
# Options: 
#  --device-id TEXT
#  --device-alias TEXT [Not supported Yet}
#  --profile TEXT: [default: default]
```

### Usage

```
$ damda get-device --device-id  Damda-V2-J328hJTXRZK2H72dLdjE7A
{'coreDeviceThingName': 'Damda-V2-J328hJTXRZK2H72dLdjE7A', 'coreVersion': '2.5.3', 'platform': 'linux', 'architectu
re': 'arm', 'status': 'HEALTHY', 'lastStatusUpdateTimestamp': '2022-02-25 00:57:18.001000+00:00', 'tags': {}}
```

## list-devices

Retrieves the damda device list.

### Command

```
$ damda list-devices [OPTIONS]
# Options:
#  --profile TEXT: [default: default]
```

### Usage

```
$ damda list-devices
['DAMDA-xdX0xL86QEmhzEQZNJ4Qxg', 'Damda-V2-J328hJTXRZK2H72dLdjE7A']
```

## list-installed-components

* Retrieves the list of components installed in the device.
* Either --device-id or --device-alias is required.
  * **However, --device-alias is not yet supported**.

### Command

```
$ damda list-installed-components [OPTIONS]
# Options: 
#  --device-id TEXT
#  --device-alias TEXT
#  --profile TEXT: [default: default]
```

### Usage

```
$ damda list-installed-components --device-id  Damda-V2-J328hJTXRZK2H72dLdjE7A
[{"component_id":"aws.greengrass.Nucleus","version":"2.4.0","state":"FINISHED"},
{"component_id":"aws.greengrass.clientdevices.IPDetector","version":"2.0.2","state":"RUNNING"},
{"component_id":"com.example.first","version":"1.0.3","state":"FINISHED"},
{"component_id":"aws.greengrass.Cli","version":"2.4.0","state":"RUNNING"}]
```
