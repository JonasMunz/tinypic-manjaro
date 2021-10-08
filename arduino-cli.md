# Setting up Arduino-cli

1. Install arduino-cli
   ```
   sudo pacman -S arduino-cli
   ```
2. Update index
   ```
   arduino-cli core update-index
   ```
3. Initiate configuration folder
   ```
   arduino-cli config init
   ```
   
4. Add esp link
   ```
   <editor> ~/.arduino15/arduino-cli.yaml
   ```
   
   In * addittional_urls* add the link: https://dl.espressif.com/dl/package_esp32_index.json
   ```
   board_manager:
       additional_urls: [https://dl.espressif.com/dl/package_esp32_index.json]
   daemon:
      ...
   ```
5. Update index to take into account esp32
   ```
   arduino-cli core update-index
   ```
6. Install libraries
   - arduino-cli lib install ArduinoWebsockets
   - arduino-cli lib install "TinyPICO Helper Library"
7. Install ESP32
   ```
   arduino-cli core install esp32:esp32
   ```
8. Install pyserial
   ```
   pip install pyserial
   ```
9. Create new sketc/arduino environment
   ```
   arduino-cli sketch new <name-of-your-sketch>
   
   arduino-cli sketch new test-sketch
   ```
10. Compile
   While under your root folder of your sketch
   ```
   arduino-cli compile --fqbn esp32:esp32:tinypico <sketch-location>
   
   arduino-cli compile --fqbn esp32:esp32:tinypico .
   ```
   
   It may take a while.
12. Add user to *uucp* group.
   ```
   sudo usermod -a -G uucp
   ```
   
   Log out and log in for the change to take effect
13. Upload sketch to arduino
   ```
   arduino-cli upload --port <device-port> --fqbn esp32:esp32:tinypico <sketch-location>
   
   arduino-cli upload --port /dev/ttyUSB0 -- fqbn esp32:esp32:tinypico .
   ```

# Commands
* arduino-cli board list - Lists all board available and their port.
* arduino-cli lib search <lib-name> - searches for the name of the library
* arduino-cli core search <board-name> - searches for the name of the core to install (esp32:esp32)
* arduino-cli board listall - lists all boards and their FQBN (esp32:esp32:tinypico)

# Resources
* https://www.survivingwithandroid.com/arduino-cli-compile-upload-manage-libraries-cores-boards/
* https://dev.to/stepanvrany/esp32-with-arduino-cli-36mh
* https://create.arduino.cc/projecthub/B45i/getting-started-with-arduino-cli-7652a5
