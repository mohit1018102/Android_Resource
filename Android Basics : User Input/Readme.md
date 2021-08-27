# Making An App Interactive
1. Look at the <a href="https://s3.amazonaws.com/video.udacity-data.com/topher/2017/July/595ab9de_common-android-views-cheat-sheet/common-android-views-cheat-sheet.pdf">Common Views cheat sheet</a>
1. <a href="https://www.jetbrains.com/help/idea/reformat-and-rearrange-code.html">How to reformat source code</a>  *code> reformat code* -> selected text **to reformat the code: fix the spacing and tabs.**
2. <a href="https://www.jetbrains.com/help/idea/reformat-and-rearrange-code.html">How to rearrange source code</a> *code>rearrange code*-> selected text **order the attribute according to the android studio guidelines.**
3. <a href="https://developer.android.com/studio/intro?utm_source=udacity&utm_medium=course&utm_campaign=android_basics#key-commands">Helpful keyboard shortcuts</a> for Android Studio
4. <code>android: textAllCaps="true"</code> use this attribute to capitalize your text, it is flexible way to change text format accord to need.
5. **For Windows, go to File > Settings > Editor > General > Auto Import** : To enable auto complete.
6. DDMS stands for Dalvik Debug Monitor Server, and is a tool in Android to help you debug your app.**(eclipse MAT support DDMS)(deprecated for  android studio)(used to find Memory Leaks, crashes etc).**
7. <a href="https://developer.android.com/studio/debug?utm_source=udacity&utm_medium=course&utm_campaign=android_basics">Debugging your code in Android Studio :</a> **add breakpoint to debug app.** *(just like dry run)*
8. **Project : just java, Screenshot of desired layout.**
    * **ViewGroup: LinearLayout -> orientation: vertical**  
        * TextView
        * **LinearLayout -> orientation: horizontal**
          * Button, TextView, Button.
        * TextView 
        * TextView
        * Button



      

<img src="justjava.png" width="350dp" height="600dp"/>

## Project code : https://github.com/udacity/Just-Java

# Practice set 2 : Court Counter app 
1. `android: gravity=` **align view inside view's boundary like center horizonal, vertical horizonal, center etc.**
2. <code>android: layout_gravity=</code> **align view inside layout's boundary like center horizonal, vertical horizonal, center etc**
3. res>values>style.xml or theme res<br>
   
```xml

   <item name="colorPrimary">@color/orange</item>                    // used to set title bar background color.
   <item name="colorPrimaryDark">@color/orange</item>"</code>        //used to set top bar background color.
```
  
4. `getSupportActionBar().setTitle(Html.fromHtml("<fontcolor=\"black\">"+ getString(R.string.app_name)+"</font>"));`  used to change title bar text color.
5. **Project : Court Counter, Screenshot of desired layout.**
    * **ViewGroup: RelativeLayout**    
      * **LinearLayout -> orientation: horizontal**
        * **LinearLayout -> orientation: vertical**
            * TextView,TextView, Button :onClick, Button :onClick, Button :onClick.
        * `<View layout_width="1dp" layout_height="match_parent"/>`
        * **LinearLayout -> orientation: vertical**
            * TextView,TextView, Button :onClick, Button :onClick, Button :onClick.
      *  Button :onClick

 ### Screenshots of app
 
<img src="coutcounter.png" width="300dp" height="600dp"/>  <img src="courtcounter2.png" width="300dp" height="600dp"/>
## Project Code: https://github.com/udacity/Court-Counter

# OOPS PART 1
1.Here are some helpful links:
   * <a href="https://developer.android.com/guide/topics/resources/providing-resources?utm_source=udacity&utm_medium=course&utm_campaign=android_basics">Resources Overview</a>
   * <a href="https://developer.android.com/guide/topics/resources/providing-resources?utm_source=udacity&utm_medium=course&utm_campaign=android_basics#Accessing">Accessing Resources</a>
   * <a href="https://developer.android.com/guide/practices/screens_support.html?utm_source=udacity&utm_medium=course&utm_campaign=android_basics">How to Support Multiple Screens</a>
   * <a href="https://developer.android.com/guide/topics/resources/providing-resources.html?utm_source=udacity&utm_medium=course&utm_campaign=android_basics">Providing Resources</a>
2. Access Resources
   * In java, : `R.<resource_type>.<resource_name>`
   * In xml, : `@<resource_type>/<resource_name>`
3. Parsing layout.xml file
   * Creates a Hierarchy of java objects
   * Inflates the objects like LinearLayout, TextView etc to form a view hierarchy.
   * Objects have various method to interact with these objects.
<img src="view.png">

4. To see Classes code enable extension : **Chrome web store >> search >> Android SDK Search** : https://chrome.google.com/webstore/detail/android-sdk-search/elihjfnjglabmkeonphlglkpjppchoco?hl=en-US
5. ```java 
   public T findViewById (int id)  //returns view object
   ```
6. Red Lines are detailed specification of a design like spacing, padding etc.


# OOPS PART 2
1. ```xml
    //use Checkbox.isChecked() to know the state of the checkbox.
     <CheckBox
         android:id="@+id/notify_me_checkbox"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:text="@string/notify_me"
         android:textAppearance="?android:textAppearanceMedium" />
    ```
 2. **EDIT >> Indent Selection** :~ to indent selected text.
 3. ```xml
          <ScrollView   
               android:layout_width="match_parent"  
               android:layout_height="wrap_content"  
               android:id="@+id/scrollView">
               // Layout and views........
          </ScrollView>
          
           <HorizontalScrollView  
            android:layout_width="match_parent"  
            android:layout_height="60dp"  
            android:id="@+id/horizontalScrollView"> 
                // Layout and views........
            </HorizontalScrollView> 
            
     ```
  4. ```xml
      <EditText
         android:id="@+id/album_description_view"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:hint="Name"                              // set hint for user 
         android:inputType="text" />                     // allows only Characters
      ```
   5. `public Editable getText ()` 
   6. How to set emoji by unicode in a textview?
      ```java
             // replaced 'U+' by '0x'
             // Example: replace 'U+1F60A' by '0x1F60A'
             int unicode = 0x1F60A;
             String emoji = getEmojiByUnicode(unicode)
             String text = "So happy "
             textview.setText(text + emoji);
            ...
            public String getEmojiByUnicode(int unicode){
                 return new String(Character.toChars(unicode));
             }
         
             ...
            output: So happy 😊
      ```
   7. Intent : Intent as a message specifying some operation to be performed
         * Action, Data, Category, Component, Extras.
   
  8. <a href="https://developer.android.com/guide/components/intents-common.html?utm_source=udacity&utm_medium=course&utm_campaign=android_basics">Common Intents Guide</a>
  9. Compose mail
  ```java
      Intent intent = new Intent(Intent.ACTION_SEND);
      intent.setType("*/*");
      intent.putExtra(Intent.EXTRA_SUBJECT, "just java order for "+ name);
      intent.putExtra(Intent.EXTRA_TEXT, orderSummary);
      if (intent.resolveActivity(getPackageManager()) != null) { // check for apps that support ACTION_SEND intent
           startActivity(intent);
      }
  ```
  
 
10. addition resources : https://classroom.udacity.com/courses/ud836/lessons/4584545214/concepts/a573bb40-2b12-437a-969f-185a45a3af2b

<img src="justjava2final.png" width="350dp" height="600dp"/>

## Project code : https://github.com/udacity/Just-Java
  
