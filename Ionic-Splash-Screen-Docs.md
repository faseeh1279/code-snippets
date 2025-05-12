# Recommended Method for creating splash screen is by lottie animation 
### Create the animation in lottie creater and then export it in json format. 

### Follow the following steps 

#### 1. Open the Lottie Files Github Page and Copy the Lottie Dependency from there 

#### 2. After Copying the Lottie Dependency `paste` it into the `build.gradle` module (app) file. 

#### 3. Create a new `SplashActivity` in the com.package The Activity should be in `kotlin` language. 

#### 4. After creating the `SplashActivity` along with the `Activity_Splash.xml` file. Paste the Following Code There

#### 5. `Activity_Splash.xml` file code.  

```bash 

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout  xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".SplashActivity">
  <!-- Lottie Animation View -->
  <com.airbnb.lottie.LottieAnimationView
    android:id="@+id/lottie_animation_view"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_centerInParent="true"
    android:layout_alignParentTop="true"
  android:scaleType="centerInside"
  android:layout_alignParentBottom="true"
  android:visibility="visible"/>


</RelativeLayout>

```


#### 6. `SplashActivity.kt` code 
```bash 

package com.example.blooddonation

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat
import com.airbnb.lottie.LottieAnimationView
import android.os.Handler
import android.content.Intent
import android.view.Window

class SplashActivity : AppCompatActivity() {
  lateinit var lottieAnimationView: LottieAnimationView

  override fun onCreate(savedInstanceState: Bundle?) {
    // Set NoActionBar theme programmatically
    supportRequestWindowFeature(Window.FEATURE_NO_TITLE)
    setTheme(com.getcapacitor.android.R.style.AppTheme_NoActionBar)
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_splash)

    // Find the LottieAnimationView in the layout
    lottieAnimationView = findViewById(R.id.lottie_animation_view)

    // Set the animation
    lottieAnimationView.setAnimation(R.raw.blooddonationsplashscreen)

    // Play the animation
    lottieAnimationView.playAnimation()

    // Delay to navigate to the main activity
    Handler().postDelayed({
      val intent = Intent(this@SplashActivity, MainActivity::class.java)
      startActivity(intent)
      finish()
    }, 3000)  // Adjust delay according to your needs
  }
}


```


#### 7. After that open the `Manifest.xml` file and copy paste the following code there 

```bash 
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
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
            <meta-data
                android:name="com.google.android.gms.client_id"
                android:value="YOUR_WEB_CLIENT_ID_HERE" />
        </provider>
    </application>

</manifest>

```