# Adding Menu bar

1. An Activity can inflate a menu resource file, and display the menu in the app bar. So next, let's define our menu items in a new menu resource file:

* In res/menu/main.xml:
```xml
     <menu xmlns:android="http://schemas.android.com/apk/res/android"
         xmlns:app="http://schemas.android.com/apk/res-auto"
         xmlns:tools="http://schemas.android.com/tools"
         tools:context="com.example.android.quakereport.EarthquakeActivity">
         <item
             android:id="@+id/action_settings"
             android:title="@string/settings_menu_item" 
             android:icon="@drawable/ic_filter"
             android:orderInCategory="1"
             app:showAsAction="ifRoom" />
     </menu>
```

```java
Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.main, menu);
    return true;
}

@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();
    if (id == R.id.action_settings) {
        Intent settingsIntent = new Intent(this, SettingsActivity.class);
        startActivity(settingsIntent);
        return true;
    }
    return super.onOptionsItemSelected(item);
}
```

# Shared Preferences

1. A preference is really just a string key associated with a primitive type, String, or set of Strings. Android will hold onto that data for you even when the app is closed, and even if the phone is turned off. Android provides a SharedPreferences class to make getting and setting preferences straight-forward.
2.  SharedPreferences handles all the details of reading and writing preference data to the persistent storage (which is a file) on the device.

### Put Data
```java
        SharedPreferences sharedPreferences= getSharedPreferences("app",MODE_PRIVATE);
        SharedPreferences.Editor editor=sharedPreferences.edit();
        editor.putString("minmag",magnitude+"");
        editor.apply();
```

### Get Data

```java
        sharedPreferences sharedPrefs = getSharedPreferences("app",MODE_PRIVATE);
        String minMagnitude = sharedPrefs.getString("minmag","5");
```

