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



