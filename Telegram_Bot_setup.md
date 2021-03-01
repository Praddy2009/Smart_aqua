Now since we want to use telegram bot feature to control our IoT device so for that we have to do some initialization setup on Arduino IDE.

Steps:
1. Setting up Telegram Bot Libraries
    
    - Now in Arduino IDE, `Sketch` -> `Include Library` -> `Manage Libraries` and search for telegram.
    - Install `Universal Telegram Bot`(If it asks you to install JSON dependeny then click on Install all).
    - Search for json and make sure `ArduinoJson` is installed.

2. Getting the telegram Bot Token
  
    - Open telegram app and search for `BotFather`. Click on the account with blue tick.
    - Tap `Start`
    - Type `/newbot` to create new bot.
    - Give the name to your bot.
    - Give username to your bot. It's should end with `bot` in name.
    - Now at (1) it gives you the bot interface link and (2) provides you the HTTP API Key.Keep both the things private to yourself.
    
       ![image](https://user-images.githubusercontent.com/43271546/109471927-7e25f800-7a97-11eb-9105-85cefa454995.png)

    
3. Now setup in Arduino IDE
    
    - In Arduino IDE, `File` -> `Exampels` -> `Universal Telegram Bot`-> `ESP8266` -> `Flash LED`
    - Now fill the SSID,Password and API Key.
    - Compile and Upload.
    - On Telegram open the bot you made and `Start`
