
## Let's first create a realtime database

1. Visit : [Firebase Console](https://console.firebase.google.com)
2. Create a `new project`. Give it a unique name and disable analytics option(as we don't need them in this project).

   ![image](https://user-images.githubusercontent.com/43271546/110456974-2cf9b200-80f0-11eb-883f-4be2bbb9639c.png)

3. Select `Realtime Database` option and `Create Database`

   ![image](https://user-images.githubusercontent.com/43271546/110457767-fd977500-80f0-11eb-868a-554fac3c8dcb.png)

4. Set the Realtime Database Location to `United States(us-central-1)` and choose `Start in Test Mode`

5. Note down the URL to do API call. In Test Mode anyone can query at this API to fetch JSON data so be sure not to do the same at production level.

   ![image](https://user-images.githubusercontent.com/43271546/110458731-1ce2d200-80f2-11eb-9c3d-ce771505290c.png)

And we are done for now with Firebase.

<hr />

## Setting Up Arduino IDE for NodeMCU ESP8266

1. To setup Arduino IDE for NodeMCU - [Visit](https://github.com/Praddy2009/Smart_aqua/blob/main/IDE_Setup.md)
2. Open `Sketch` -> `Manage Library` -> `Manage Libraries` and install `ArduinoJson`
3. Now to setup firbase we need to install Library [Link](https://github.com/FirebaseExtended/firebase-arduino). Download as zip.
4. Open `Sketch` -> `Manage Library` -> `Add .ZIP library` navigate your downloaded zip and add it.
