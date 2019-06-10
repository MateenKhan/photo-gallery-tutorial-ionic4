# Ionic v4 Tutorial: Photo Gallery app

A tutorial app that walks the user through creating a Photo Gallery app. We begin with the Ionic "tabs" starter app, incrementally converting the About tab to a Photo Gallery experience.

## Structure
The complete source code is contained within. Please follow along with the [complete guide here](https://beta.ionicframework.com/docs/developer-resources/guides/first-app-v4/intro/).

## How to Run Locally
* Clone this repo.
* Open a terminal window, and navigate to this repo on the filesystem.
* Run "npm install" to install all required project dependencies. 
* Run "ionic serve" to run the app in a web browser locally.

## How to build and deploy apk
* https://ionicframework.com/docs/v1/guide/publishing.html
* or
* https://ionicframework.com/docs/v3/intro/deploying/
* run below commands (you may have to configure your system which is your task :) )
#* ionic cordova build --release android
* ionic cordova build android --prod --release
#* keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
* keytool -genkey -v -keystore my-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias my-alias
#* (#* keytool -importkeystore -srckeystore my-release-key.jks -destkeystore my-release-key.jks -deststoretype pkcs12)

#* jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.keystore ./platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk alias_name
* jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.jks ./platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk my-alias
#* zipalign -v 4 ./platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk app.apk
* zipalign -v 4 ./platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk HelloWorld.apk
* apksigner verify HelloWorld.apk
