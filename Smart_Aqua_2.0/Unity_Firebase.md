## Firebase Setup

1. Visit: [Firebase Console](https://console.firebase.google.com/)
2. Create a `Create a project`/`Add project`. Give it a unique name and disable analytics option(as we don't need them in this project).
3. Tap on Unity icon. 

    ![image](https://user-images.githubusercontent.com/43271546/111111549-8cd6d980-8584-11eb-94a9-c3586c30f97c.png)

    In case you already have a project setup then the Unity icon could be found in `⚙️`->`Project Settings`-> `General` -> `Your Apps`

4. Now lets do register our app
    - Select the target platform (Android in this case). For package name write in format `com.company.app` it uniquesly identifies your app.Also note it down somewhere.
      
      ![image](https://user-images.githubusercontent.com/43271546/111111899-2e5e2b00-8585-11eb-915f-cf4c2e39a7cf.png)

    - Now download the json package

      ![image](https://user-images.githubusercontent.com/43271546/111112046-7e3cf200-8585-11eb-9aaa-87081cbef0ea.png)

    - Now download Unity SDK

      ![image](https://user-images.githubusercontent.com/43271546/111112166-b2181780-8585-11eb-8be6-1a49f176fcb4.png)

    - Click on `Continue to Console.`

5. It's time to create Realtime Database.
    - Visit: [Firebase Console](https://console.firebase.google.com/)
    - Click on `Realtime Database`

      ![image](https://user-images.githubusercontent.com/43271546/111112428-2a7ed880-8586-11eb-8a3e-9d3770e4eed3.png)

    - Click on `Create database`

      ![image](https://user-images.githubusercontent.com/43271546/111112522-4d10f180-8586-11eb-98b3-76105ea4973a.png)

    - Select Database location: `United States (us-central1)`	& select `Start in Locked mode`
    - Create a variable and name it. Note down the variable name and the Database URL.

      ![image](https://user-images.githubusercontent.com/43271546/111112940-040d6d00-8587-11eb-9d02-7c2b44cd294b.png)

    - Visit Rules and meake read and write to `true` and publish.

      ![image](https://user-images.githubusercontent.com/43271546/111113113-4636ae80-8587-11eb-8ff7-b69712fca76f.png)

<hr />

## Unity Part

### Unity Setup
1. Create a Unity project.
2. Platform Settings
    - Open `File` -> `Build Settings`
    - Select `Android` and `Switch Platform`

      ![image](https://user-images.githubusercontent.com/43271546/111114975-058c6480-858a-11eb-8704-8d9bfb1f39b3.png)

    - Click `Add Open Scenes` and then click on `Player Settings`.
    - In `Player Settings` -> `Other Settings` -> `Package Name` -> Set to the package name we specified in firebase.You can also find the package name in Firebase console project settings.
    - Set `Minimum API level` to 25.
    - Set `API Compatibility level` to `.NET 4.x` if not set.
    
      ![image](https://user-images.githubusercontent.com/43271546/111116125-8f88fd00-858b-11eb-9ca3-adc7cb493290.png)
    
3. Import the packages:
    - JSON : Import the downloaded json file into Assets folder
      
       ![image](https://user-images.githubusercontent.com/43271546/111114079-c1e52b00-8588-11eb-864e-7379f411fef1.png)

    - Import FirebaseDatabase from the downloaded Unity package zip(Obviouslly you need to unzip it before).Since we using dot NET 4 so import it from `dotnet4`
      
      ![image](https://user-images.githubusercontent.com/43271546/111116315-dd056a00-858b-11eb-94e2-1acb7004032b.png)

    - If it asks to resolve some dependencies `Enable` them.  
        
3.  


      
