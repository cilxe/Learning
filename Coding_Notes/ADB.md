
[<h1>Android Debug Bridge (adb)</h1>](https://developer.android.com/tools/adb)

## Common Rules on Windows
```
adb start-server
adb kill-server
```

## Connect adb wirelessly
```
adb tcpip   $PORT_NUMBER$
adb connect $IP_ADDRESS$
```

## Set up port forwarding
```
adb forward tcp:6100 tcp:7100
adb forward tcp:6100 local:logd
```

## Show connected devices
```
adb devices
```

## Reboot connected device
```
adb reboot
```

## Install an android package from a remote (PC)
```
adb install "file.apk"
```

## Push & pull file between Windows and Android device
```
adb pull remote local
adb push local remote

adb push "%path%/file.txt" /sdcard/file.txt
adb pull /sdcard/XXX E:/Files/
```

## Enter shell mode
```
adb shell
```

## Call package manager (pm)
```
# Install a package
adb shell pm install [options] path

# Uninstall a package
adb shell pm uninstall -k --user 0 $PACKAGE_NAME$

# Enable a package
adb shell pm enable $PACKAGE_NAME$

# Disable a package
adb shell pm disable-user $PACKAGE_NAME$

# Force-stop a running package
adb shell am force-stop $PACKAGE_NAME$



# Show package details
adb shell dumpsys package $PACKAGE_NAME$

# Show package installed path
adb.exe shell pm path $PACKAGE_NAME$

# List all packages
adb shell pm list-packages

# List all system packages
adb shell pm list packages -s

# List all other packages
adb shell pm list packages -3

# List all enabled packages
adb shell pm list packages -e

# List all disabled packages
adb shell pm list packages -d

# List all users
adb shell pm list users
```


# Reinstall a system package that uninstalled with adb
```
adb shell cmd package install-existing $PACKAGE_NAME$
``