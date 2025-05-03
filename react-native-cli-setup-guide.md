# Setting up react-native cli guide

## Adding Firebase

1. Install reactive firebase modules
    ```bash
    npm install --save @react-native-firebase/app
    ```
2. Setup Android project
  
    Generate android credentials
    On the firebase console, create an android project with the folllowing information:
    - Get package name from your react native project found inside of the `namespace` field in `/android/app/build.gradle`

    - Nickname name should be a short app name

    - Generate the Debug signing         certificate SHA-1 by with `cd android && ./gradlew signingReport`. This generates two variant keys. You have to copy both 'SHA1' and 'SHA-256' keys that belong to the 'debugAndroidTest' variant key option. Then, you can add those keys to the 'SHA certificate fingerprints' on your app in Firebase console.
    - Download the `google-services.json` file and place it inside of your project at the following location: `/android/app/google-services.json`.

2. Configure Firebase with Android credentials
  
    This requires modification to two files in the Android directory

    First, add the google-services plugin as a dependency inside of your `/android/build.gradle` file

  ```  buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.4.2'
    // Add me --- /\
  }
}
```

Lastly, execute the plugin by adding the following to your `/android/app/build.gradle` file
``` 
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services' // <- Add this line
```

Source: [React Native Firebase](https://rnfirebase.io/)

## Adding React Native Image Picker (react-native-image-crop-picker)
### Installation
```npm i react-native-image-crop-picker --save
```
### Configuration
[See documentation](See documentation](https://www.npmjs.com/package/react-native-image-crop-picker)


