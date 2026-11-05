# IS TATTOO CRM — Android MVP

An Android Studio project for a tattoo studio client CRM.

## Included in this first MVP
- Add and search clients by name or phone
- Client profile with notes
- Bonus points: add/deduct manually
- Attach multiple photos to a client profile (photo URIs are stored)
- Schedule a local reminder after a chosen number of minutes
- Open the phone's SMS app with the client's number and a starter message
- Local Room database

## Build the APK
1. Install Android Studio (Hedgehog or newer).
2. Open this folder in Android Studio.
3. Allow Gradle sync to finish.
4. Connect an Android phone with USB debugging enabled, or start an emulator.
5. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. Android Studio will show the generated APK location, usually `app/build/outputs/apk/debug/app-debug.apk`.

Command line (with Android SDK installed):
```bash
./gradlew assembleDebug
```

## Important notes
- This is a first working MVP source project, not a precompiled APK. An Android SDK/Gradle build environment is required to produce the APK.
- SMS opens the device's messaging app; the user reviews and sends the message. Automatic SMS delivery requires an SMS gateway and credentials.
- Reminder scheduling uses WorkManager, so Android may deliver notifications later than the exact requested minute due to battery optimizations.
- Photos are associated with the client by URI. For long-term reliability, use Android's system photo picker and persist access; some providers may revoke access.
- Data is stored locally on this device. There is no cloud sync, backup service, multi-user access, or encryption in this MVP.
- Before production use, add database export/backup, stronger photo storage, privacy controls, and tests.
