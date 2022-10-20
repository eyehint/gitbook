# Deployment

Commands to check component deployment and deployment results

* Create a deployment to install components on devices.&#x20;
* Either --device-id or --device-alias is required.
  * However, --device-alias is not yet supported.
* The configuration file follows the following structure:&#x20;
  * JSON file
  * COMPONENT\_ID
    * ex) com.example.first"
  * COMPONENT\_VERSION
    * ex) "1.0.2"

```
#deployment_config.json
{
    "public": {
        "<COMPONENT_ID>": {
            "componentVersion": "COMPONENT_VERSION"
        },
    },
    "custom": {
        "<COMPONENT_ID>": {
            "componentVersion": "COMPONENT_VERSION"
        },
        "<COMPONENT_ID>": {
            "componentVersion": "COMPONENT_VERSION"
        }
    }
}
```

* See the list of public components as follows:

```
$ damda list-components --type PUBLIC
```

* See the list of custom components as follows:

```
$ damda list-components --type CUSTOM
```

### Command

```
$ damda create-deployment [OPTIONS]
# Options:
#  --device-id TEXT
#  --device-alias TEXT
#  --configuration-file PATH: [required]
#  --profile TEXT: [default: default]
```

### Usage

```
# Deployment_config.json
{
    "public": {},
    "custom": {
        "com.example.first": {
            "componentVersion": "1.0.2"
        }
    }
}
```

```
$ damda create-deployment --device-id  Damda-V2-J328hJTXRZK2H72dLdjE7A --configurat
ion-file ./deployment_config.json
```

## list-deployments

* Retrieves the list of deployment results of a specific device.
  * Either --device-id or --device-alias is required.
    * However, --device-alias is not yet supported.

### Command

```
$ damda list-deployments [OPTIONS]
# Options:
#  --device-id TEXT
#  --device-alias TEXT
#  --profile TEXT: [default: default]
```

### Usage

```
$ damda list-deployments --device-id  Damda-V2-J328hJTXRZK2H72dLdjE7A
[{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"7","deploymentStatus":"COMPLETED","isLatestForTarget":true,"creationTimestamp":"2022-02-25 06:42:42.197000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"6","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 06:39:37.921000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"5","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 06:32:12.059000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"4","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 06:26:22.710000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"3","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 06:23:17.355000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"2","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 06:04:16.288000+00:00"},
{"deploymentName":"Damda-V2-J328hJTXRZK2H72dLdjE7A","revisionId":"1","deploymentStatus":"INACTIVE","isLatestForTarget":false,"creationTimestamp":"2022-02-25 05:55:02.733000+00:00"}]
```
