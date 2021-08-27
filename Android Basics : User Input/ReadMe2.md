# Localization 

1. See this <a href="https://developer.android.com/distribute/best-practices/launch/localization-checklist?utm_source=udacity&utm_medium=course&utm_campaign=android_basics#manage-strings">article</a> for an in-depth explanation of how to manage strings.
2. **Support different languages and cultures : https://developer.android.com/training/basics/supporting-devices/languages**
3. Create locale directories and resource files
   To add support for more locales, create additional directories inside res/. Each directory's name should adhere to the following format:
   ```xml
        <resource type>-b+<language code>[+<country code>]
          
          eg:
          
          MyProject/
                    res/
                        values/
                                strings.xml
                        values-b+es/
                                strings.xml
                        mipmap/
                                country_flag.png
                        mipmap-b+es+ES/
                                country_flag.png
    ```
 4. Create different language/ country resources
 5. Language of the app changes with the system language. by default English language is used.
 
 
 # String Resources
 
1. XML file saved at res/values/strings.xml:
```xml
    <?xml version="1.0" encoding="utf-8"?>
    <resources>
           <string name="hello">Hello!</string>
     </resources>
```
2. This layout XML applies a string to a View:
```xml
      <TextView
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:text="@string/hello"
        />
```
3. This application code retrieves a string:
```java
     String string = getString(R.string.hello);
       or
     String string = getResources().getString(R.string.hello);//old
```

# Style and Theme
1. Android developer site : https://developer.android.com/guide/topics/ui/look-and-feel/themes
2. Style applies to View elements in xml.
3. Themes apllies to entire Activity or application. (To all the view inside an app or activity). eg: light, dark theme.
  ### STYLE
  * you can inherit the Android platform's default text appearance and modify it as follows:
    ```xml
             <style name="GreenText" parent="@android:style/TextAppearance">
                <item name="android:textColor">#00FF00</item>
             </style>
    ```
   *  The following style inherits all styles from the GreenText style above and then increases the text size:
     
       ```xml
            <style name="GreenText.Large">
                   <item name="android:textSize">22dp</item>
             </style>
       ```
2. You can apply the style to a view as follows:
```xml
    <TextView
      style="@style/GreenText"
    ... />
```

  ### Theme
  * Using the Material Theme: http://android-doc.github.io/training/material/theme.html
  ```xml
   <resources>
        <!-- inherit from the material theme -->
        <style name="AppTheme" parent="android:Theme.Material">
            <!-- Main theme colors -->
            <!--   your app branding color for the app bar -->
            <item name="android:colorPrimary">@color/primary</item>
            <!--   darker variant for the status bar and contextual app bars -->
            <item name="android:colorPrimaryDark">@color/primary_dark</item>
            <!--   theme UI controls like checkboxes and text fields -->
            <item name="android:colorAccent">@color/accent</item>
        </style>
</resources>
```
2. You can apply the theme to an app as follows:
```xml AndroidManifest/.xml
    <manifest ... >
    <application android:theme="@style/Theme.AppTheme" ... >
    </application>
   </manifest>
```
3. You can apply the theme to an activity as follows:
```xml
     <manifest ... >
    <application ... >
        <activity android:theme="@style/Theme.ActTheme" ... >
        </activity>
    </application>
</manifest>
```
    
  
