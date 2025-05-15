# Google Sign-In | Authenticate using Google in Angular + Ionic 

### Ionic Capacitor Packages required `codetrixstudio/capacitor-google-auth`

#### In order to run the google signin on android real device all you have to do is to create a `Project` on `Google Cloud Console`. 


#### After that add the `SHA1-Fingerprint` from your `android studio` using the command. 
```bash
./gradlew signingReport
```

#### After that add the `package name` of your project which you would find in the `build.gradle` `app:module` in the `Android Studio`. 

#### After adding the package name go to the `capacitor.config.ts` file. The code should like as follows: 

```bash 
import type { CapacitorConfig } from '@capacitor/cli';
const config: CapacitorConfig = {
  appId: 'com.innoppia.blooddonation',
  appName: 'BloodDonationApp',
  webDir: 'www',
  android: {
    allowMixedContent: true,
  },
  plugins: {
    GoogleAuth: {
      clientId: '725570138049-rqmt497fmq4cjqbj640u9mr11tee3nfv.apps.googleusercontent.com',
      scopes: ['profile', 'email'],
      forceCodeForRefreshToken: false
    }
  }
};
export default config;
```


#### After adding that you would have to add `package name` in the `AndroidManifest.xml` file as well. 
```bash 
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="com.innoppia.blooddonation">
  <!-- Permissions -->
  <uses-permission android:name="android.permission.INTERNET" /> <!-- Geolocation API -->
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
  <uses-feature android:name="android.hardware.location.gps" />


  <application
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
    android:theme="@style/AppTheme">
    <activity
      android:name=".SplashActivity"
      android:exported="true">
      <intent-filter>
        <action android:name="android.intent.action.MAIN" />

        <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
    </activity>
    <activity
      android:name=".MainActivity"
      android:configChanges="orientation|keyboardHidden|keyboard|screenSize|locale|smallestScreenSize|screenLayout|uiMode|navigation"
      android:exported="true"
      android:label="@string/title_activity_main"
      android:launchMode="singleTask"
      android:theme="@style/AppTheme.NoActionBarLaunch"/>

    <provider
      android:name="androidx.core.content.FileProvider"
      android:authorities="${applicationId}.fileprovider"
      android:exported="false"
      android:grantUriPermissions="true">
      <meta-data
        android:name="android.support.FILE_PROVIDER_PATHS"
        android:resource="@xml/file_paths" />
    </provider>
  </application>

</manifest>

```

#### You would have to use both the `AndroidClientID` as well as the `WebClientID` in order to make that to work. 
#### In most cases the ID used is the `WebClientID`


> [!NOTE]  
> While using `Google Signin` on `Android Project` use the `SHA1-Fingerprint` of the google publish while testing. 