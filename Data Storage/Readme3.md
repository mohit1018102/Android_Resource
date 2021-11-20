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

```java

public final class PetContract {

   .......
    public static final String CONTENT_AUTHORITY = "com.technomaniacs.android.mypet";
    public static final Uri BASE_CONTENT_URI = Uri.parse("content://" + CONTENT_AUTHORITY);
    public static final Uri CONTENT_URI = Uri.withAppendedPath(BASE_CONTENT_URI, PetEntry.TABLE_NAME);
    .....
}

```

# URI Matcher

## content://com.technomaniacs.android.mypet/# --> number of any length
## content://com.technomaniacs.android.mypet/* --> string of any length

<p align="center">
        <img src="img/urim1.PNG" />
        <img src="img/urim2.PNG" />
        <img src="img/urim3.PNG" />
</p>

```java

    /** URI matcher code for the content URI for the pets table */
    private static final int PETS = 100;

    /** URI matcher code for the content URI for a single pet in the pets table */
    private static final int PET_ID = 101;

    /**
     * UriMatcher object to match a content URI to a corresponding code.
     * The input passed into the constructor represents the code to return for the root URI.
     * It's common to use NO_MATCH as the input for this case.
     */
    private static final UriMatcher sUriMatcher = new UriMatcher(UriMatcher.NO_MATCH);
    static {
        sUriMatcher.addURI(PetContract.CONTENT_AUTHORITY, PetEntry.TABLE_NAME, PETS);
        sUriMatcher.addURI(PetContract.CONTENT_AUTHORITY, PetEntry.TABLE_NAME +"/#", PET_ID);
    }
```


 
