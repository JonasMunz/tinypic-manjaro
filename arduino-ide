# Setting up Arduino IDE
1. install arduino IDE
```
sudo pacman -S arduino
```

2. File -> Preferences -> Additional Board Manager.
   Add the url: https://dl.espressif.com/dl/package_esp32_index.json
   
3. Tools -> Board -> Boards manager.
   Search for esp32 and install latest version
4. Tools -> Manage Libraries:
   * ArduinoWebsockets
   * Tinypico
5. Install pyserial via pip

```
pip install pyserial
```

# Uploading code to Arduino

Add yourself to the group *uucp*

```
sudo usermod -a -G uucp <account-username>
```

# Setting up Pulseview

```
sudo pacman -S pulseview boostlibs sigrok-firmware-fx2lafw sdcc sigrok-cli
```

Reboot + disconnect logic analyzer if it does not work soon after.
There may be an error once booting up pulseview, but as long as you see **Salaea logic** you should be good to run it.

From experience, *sudo* is not needed to run pulseview.
