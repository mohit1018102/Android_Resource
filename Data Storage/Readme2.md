# Lesson 2 - Using a Database in an Android App
### git :https://github.com/udacity/ud845-Pets .

## UI-FAB
```XML
<com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/floatingActionButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"

        android:layout_marginRight="20dp"
        android:layout_marginBottom="40dp"
        android:clickable="true"
        android:src="@drawable/ic_add_pet"
        app:backgroundTint="@color/colorPrimary" <--- bg color
        app:tint="@color/white"                  <--- icon color
        tools:ignore="MissingConstraints,SpeakableTextPresentCheck" />
```

## UI -Spinner

```xml
          <Spinner
                android:id="@+id/spinner_gender"
                android:layout_height="48dp"
                android:layout_width="wrap_content"
                android:paddingRight="16dp"
                android:spinnerMode="dropdown"/>
```

```xml
<!-- value> arrays.xml-->
<resources>
    <!-- These are the options displayed in the gender drop-down Spinner -->
    <string-array name="array_gender_options">
        <item>@string/gender_unknown</item>
        <item>@string/gender_male</item>
        <item>@string/gender_female</item>
    </string-array>
</resources>
```

```java

        private void setupSpinner() {
                  
                  // Create adapter for spinner. The list options are from the String array it will use
                  // the spinner will use the default layout
                  ArrayAdapter genderSpinnerAdapter = ArrayAdapter.createFromResource(this,
                                      R.array.array_gender_options, android.R.layout.simple_dropdown_item_1line);
                 
                 // Apply the adapter to the spinner
                 mGenderSpinner.setAdapter(genderSpinnerAdapter);

    }

```

# steps to create DB

## 1. SCHEMA AND CONTRACT CLASS

```sql
SCHEMA

CREATE TABLE pets
( _id INTEGER AUTOINCREMENT PRIMARYKEY,
  name TEXT,
  breed TEXT,
  gender INTEGER,
  weight REAL
);
  
```

#### Contract class
1. A contract class is a container for constants that define names for URIs, tables, and columns. 
2. The contract class allows you to use the same constants across all the other classes in the same package.
3. This lets you change a column name in one place and have it propagate throughout your code.

```java
/** Note: By implementing the BaseColumns interface, your inner class can inherit a primary key field 
called _ID that some Android classes such as CursorAdapterexpect it to have. It's not required, 
but this can help your database work harmoniously with the Android framework.
**/
public final class PetContract {

    private PetContract()
    {
    }

    public static class PetEntry implements BaseColumns
    {
        //********table*************
        public static final String TABLE_NAME="pets";
        public static final String _ID=BaseColumns._ID;
        public static final String COLUMN_PET_NAME="name";
        public static final String COLUMN_PET_BREED="breed";
        public static final String COLUMN_PET_GENDER="gender";
        public static final String COLUMN_PET_WEIGHT="weight";

        //*********gender**********
        public static final int GENDER_UNKNOWN=0;
        public static final int GENDER_MALE=1;
        public static final int GENDER_FEMALE=2;

    }
}
```

## 2. create Database using SQLiteOpenHelper
1. Android provides a class that help us create, open and manage db and that class is SQLiteOpenHelper class.
2. what does this class do:
        * create a sqlite database when it is first accessed.
        * next times when user opens the app, Gives you a connection to that database.
        * Manages updating the database schema if version changes
3. Todo:
      * create a class that extends SQLiteOpenHelper.
      * create constants for database name and database version
      * create a constructor
      * implement onCreate()- this method is for when the database create for first time.
      * implement onUpgrade()- this method is for when the db schema of the db changes.(ex: adding new column).
        





