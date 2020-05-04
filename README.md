# EnterpriseBrowser-2.5-DevTalk
Sample apps used in the EnterpriseBrowser 2.5 DevTalk held 20th May 2020

## Starting test server

Python 3:
```bash
py -m http.server 8081
```

## Prerequisites
* Install Enterprise Browser 2.5: `adb install -r EnterpriseBrowser_signed_2.5.0.2.apk`

## Multi Session

### Shortcuts
* Modify [repo_root]/shortcuts/configs/app1/Config.xml and [repo_root]/shortcuts/configs/app2/Config.xml so the startPage parameter points to the machine you are going to host your server on (currently set to 192.168.0.2).
* Start test server from the root of the github repo on port 8081 (You can change this number but it must match the value defined in Config.xml)
* Copy the project configuration to the device from [repo_root]/shortcuts/configs/Config.xml `adb push Config.xml /storage/emulated/0/Android/data/com.symbol.enterprisebrowser/Config.xml`.  This is needed to create the shortcut files after launch.
* Create shortcuts using the shortcut tool (two tabs)
  * Configs and icons for each app can be found under [repo_root]/configs/app1 and /app2

![Configuration tool](https://raw.githubusercontent.com/darryncampbell/EnterpriseBrowser-2.5-DevTalk/master/media/shortcut_creation.png)

* Push the shortcuts to the Android device using the shortcut tool
* Launch Enterprise Browser
* Manually click 'Add Automatically' for both of the tabs.  This is required post Oreo


### Tabs

* Modify [repo_root]/tabbar/configs/tabbar.xml to point to the machine IP address you are going to host your server on (currently set to 192.168.0.2)
* Start test server from the root of the github repo on port 8081 (You can change this number but it must match the value defined in tabbar.xml)
* Push the Config.xml file to the device that enables the tabbar.  You can find this in [repo_root]/tabbar/configs/Config.xml. `adb push Config.xml /storage/emulated/0/Android/data/com.symbol.enterprisebrowser/Config.xml`
* Push the tabbar.xml file to the device `adb push tabbar.xml /storage/emulated/0/Android/data/com.symbol.enterprisebrowser/tabbar.xml`

## License
This project is protected by Zebra's EULA, as detailed in the [License.md](./License.md) file

## Contribution
Pull requests are not accepted for this project.
