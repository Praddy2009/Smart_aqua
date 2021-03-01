Initially Arduino IDE doesn't contain any support for esp8266. So we need to first install the package for esp8266.

Steps:-
  
  1. Open `File` -> `Preferencess`. And add the URL - http://arduino.esp8266.com/stable/package_esp8266com_index.json in `Additional Boards Manager URL` and then press OK.
  
     ![image](https://user-images.githubusercontent.com/43271546/109449836-6f2b4f80-7a6f-11eb-943f-83d473baf93f.png)

  2. Open `Tools` -> `Board` -> `Boards Manager` and search for esp8266 and Install it
 
     ![image](https://user-images.githubusercontent.com/43271546/109449959-c6c9bb00-7a6f-11eb-8b01-f899cf89990a.png)

  3. Select `Tools` -> `Board` -> `ESP8266 Boards` -> `NodeMCU1.0 (ESP 12E Module)`
  4. Select `Tools` -> `Ports` -> The port you attache the NodeMCU
  
Let's test our setup with a blinking sketch

Steps:-

  1. `File`-> `Examples` -> `Basics` -> `Blink`
  2. Make sure the board and port is set under tool tab
  3. `Verify` and `Upload`
  
     ![image](https://user-images.githubusercontent.com/43271546/109451308-28d7ef80-7a73-11eb-9c05-8fdf31fc8b9b.png)

