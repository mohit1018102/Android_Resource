# CONTENT PROVIDER
## Good abstraction layer between data source and UI code ( can add data validation, can modify how data is stored and UI Code is uneffected).

<p align="center">
        <img src="img/cp1.PNG" />
  </p>
  
 
 
 ## content provider is an android component that is used to share data.
  <p align="center">
        <img src="img/cp4.PNG" />
  </p>
  
 ## works wells with other android framework.
 
 <p align="center">
        <img src="img/cp2.PNG" />
  </p>
  


# Content Resolver

 <p align="center">
        <img src="img/cr2.PNG" />
  </p>
  
## Step 1: Adding ContentProvider to the App
#### https://developer.android.com/reference/android/content/ContentProvider.html?utm_source=udacity&utm_medium=course&utm_campaign=android_basics

```xml
AndroidManifest.xml

<application>
    <provider
            android:name=".db.PetProvider"
            android:authorities="com.technomaniacs.android.mypet"       // uniquely identifies the content provider on the device
            android:exported="false"                                    // exported to other apps or not
            />
</application>
```
```java
public class PetProvider extends ContentProvider {
    @Override
    public boolean onCreate() {
        return false;
    }

    @Nullable
    @Override
    public Cursor query(@NonNull Uri uri, @Nullable String[] projection, @Nullable String selection, @Nullable String[] selectionArgs, @Nullable String sortOrder) {
        return null;
    }

    @Nullable
    @Override
    public String getType(@NonNull Uri uri) {
        return null;
    }

    @Nullable
    @Override
    public Uri insert(@NonNull Uri uri, @Nullable ContentValues values) {
        return null;
    }

    @Override
    public int delete(@NonNull Uri uri, @Nullable String selection, @Nullable String[] selectionArgs) {
        return 0;
    }

    @Override
    public int update(@NonNull Uri uri, @Nullable ContentValues values, @Nullable String selection, @Nullable String[] selectionArgs) {
        return 0;
    }
}
```

## Step 2: Designing Pet Uri ( uniform resource Identifier )
### used to identify data
<p align="center">
        <img src="img/uri1.PNG" />
         <img src="img/uri2.PNG" />
               <img src="img/uri3.PNG" />
               
</p>
 
