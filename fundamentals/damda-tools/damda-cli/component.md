# Component

Commands to create/delete/list components

## create-component

Command to create compnent version.

**--source must be a zip file path of the source**

**Createing public components is not yet supported**

&#x20;   **--type PUBLIC is not supported**

The configuration file follows the following structre

Json file

|     Key     | Required | Explaination                                                                                                                        |
| :---------: | :------: | ----------------------------------------------------------------------------------------------------------------------------------- |
|      id     | Required | <p>component id<br>ex) com.example.first</p>                                                                                        |
|   version   | Required | <p>component version<br>ex) 1.0.0</p>                                                                                               |
| description | Required | <p>component description<br>ex) first application</p>                                                                               |
|  thumbnail  | Optional | <p>component thumbnail<br>The thumbnail should be in the same location as the config file(--configuration-file)<br>ex) icon.png</p> |
|    script   | Required | <p>script to run the component<br>ex) pip3 install -r requirements.txt;python3 main.py</p>                                          |
|     link    | Optional | <p>in the case of a web application, a link to access the application<br>ex) http://127.0.0.1:3000</p>                              |
|    title    | Requried | <p>component title<br><br>ex) My First App</p>                                                                                      |

### Command

```
$ damda create-component [OPTIONS]
# Options:
#  --source PATH: [required]
#  --configuration-file PATH: [required]
#  --type TEXT: [defulat: CUSTOM] [CUSTOM | PUBLIC]
#  --profile TEXT: [default: default]

```

### Usage

Recommanded Component structure (example)

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

```
# com.example.first_0.0.1.json
{
   "id":"com.example.first",
   "version": "1.0.2",
   "description": "Sample Component",
   "thumbnail": "icon.png",
   "script": "python3 {root}/first/first.py",
   "link": "",
   "title": "Frist app"
}
```

```
$ cd <COMPONENT_PROJECT_DIR>
$ damda create-component --source ./first.zip --configuration-file ./com.example.first.json
```

## delete-component

Delete all versions of a component

### Command

```
$ damda delete-component [OPTIONS]
# Options:
#  --component-id TEXT: [required]
#  --profile TEXT: [default: default]
```

###
