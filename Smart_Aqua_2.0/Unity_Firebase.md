## Let's setup Firebase Realtime database with Unity.

1. Create a new project in Unity and switch it to `Android`.
2. In `player settings` give `Company Name` and `Product Name`.
3. In `Player Setting` -> `Publishing Setting` create a Keystore.
    - Click in `Keystore Manager` 
     
      ![image](https://user-images.githubusercontent.com/43271546/111471138-9449de80-874e-11eb-8ac3-fe8d7c4f4197.png)
    
    - `Keystore` -> `CreateNew` -> `InDedicatedLocation` and fill the details.
      
      ![image](https://user-images.githubusercontent.com/43271546/111471633-1c2fe880-874f-11eb-9784-6bef164f90d6.png)

    - Add Key
    
    Note: Multiple gams/apps under same Keystore the differentiated by Alias so use that field to give it a unique name with a different password.
    
4. Now head over to [Firebase Console](https://console.firebase.google.com/) and create a new project.
  ![image](https://user-images.githubusercontent.com/43271546/111472412-edfed880-874f-11eb-88c2-d1008e5daa1e.png)

5. Give it a name and turn off analytics for now.
6. Click on the Unity Icon to add the application
    ![image](https://user-images.githubusercontent.com/43271546/111473895-80ec4280-8751-11eb-9ea9-74a91f0d7261.png)

7. Register as Android app and in Unity player Setting get the package name and paste it here.For App nick name give it any. And click on Register.
    ![image](https://user-images.githubusercontent.com/43271546/111474470-1ee00d00-8752-11eb-8d9a-274d0ec310ad.png)

8. `Next` -> `Next` -> `Continue to Console`
9. 
