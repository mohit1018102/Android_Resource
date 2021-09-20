# Q1. Where does nativeLib mapped  inside Android device?
<img src="img/nativelib.png"/>

```xml
AndroidManifest.xml

<application
        android:allowBackup="true"
        ....
        android:theme="@style/Theme.MiwokApp"
        android:extractNativeLibs="true"
        >
</application>

```

## Avoid extracting native libraries 
When building the release version of your app, package uncompressed .so files in the APK by setting android:extractNativeLibs="false" in the <application> element of your app's manifest. Disabling this flag prevents PackageManager from copying .so files from the APK to the filesystem during installation and has the added benefit of making updates of your app smaller. When building your app using Android Gradle plugin 3.6.0 or higher, the plugin sets this property to "false" by default.
