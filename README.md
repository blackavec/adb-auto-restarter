# adb-auto-restarter
ADB service auto restarting shell. really helpful if you are as lazy as i am and don't want to restart your adb service manually when it stops detecting your android phone.

# How To Use
You don't need to do much, just run the following command in order to run the shell on your system
```
# Make permission
make permission

# Lunch the app
make run
```
or
```
chmod +x adb-service
./adb-service
```

# Customize
In order to run your own additional script on every time that ADB is being restarted, you can put your shell into `custom-shell.sh` file.

# React native
I personally suggest you to add following line into your custom bash (`custom-shell.sh`) file to have a easier experience debugging React native app while it's being restarted.
```
# First find your device ID by following script
adb devices

# Second replace your device id with `<DEVICE_ID>` in next line
adb -s <DEVICE_ID> reverse tcp:8081 tcp:8081
```
Feel free to change the port number 8081 in case you are using any other ports on your packager

# important
This script file has been developed on macOSX and not sure about compatiblity on linux. test and contribution would be appreatiated