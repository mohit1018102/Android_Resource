# Android Basics: Multiscreen Apps
1. **color: https://material.io/resources/color/#!/?view.left=0&view.right=0**
2. When user tap on the app icon, android sends an intent to start your application, then that intent is handled by main activity and opens app's launcher screen.
<img src="launchcycle.png" width=700 height=400/>

## Intent
1. blog : https://www.vogella.com/tutorials/AndroidIntent/article.html#usingintents_call
2. Intents are asynchronous messages which allows you to interact with components from the same applications as well as with components contributed by other applications. For example, an activity can start an external activity for taking a picture.
3. Types of intent :
    * Implicit intent : An implicit intent specifies an action that can invoke any app on the device able to perform the action. Using an implicit intent is useful when your app cannot perform the action, but other apps probably can and you'd like the user to pick which app to use.
    
    ```java
    
        //setData() - This method is only to specifies a URI.
        //setType()- This method specifies a MIME type.
        //setDataAndType()- This method i specifies both a URI and a MIME type.
        
         Intent i = new Intent();
         i.setAction(Intent.ACTION_VIEW);
         i.setData(Uri.parse("www.tutorialspoint.com"));
         
         //verify that intent will resolve properly
         if(i.resolveActivity(getPackageManager())!=null){
               startActivity(i);
         }
           

   ```
   <br>
   <img src="implicit.PNG" width=500 height=300/>
   <br>
   * It going to connect the internal world of an application such as start activity or send data between two activities. To start new activity we have to create Intent object 
     and pass source activity and destination activity as shown below-
     
     ```java
         Intent send = new Intent(MainActivity.this, SecondActivity.class);
         startActivity(send);
     ```
     <br>
    <img src="explicit.PNG" width=500 height=300/>
   <br>

### To change Activity title bar text

```xml
 AndroidManifest.xml
<application>
   ...
    <activity
            android:name=".PhrasesActivity"
            android:label="@string/phrases"  //string displayed to user
            android:exported="true" />
   ...
                  
 </application>
```


## Event listeners
An event listener is an interface in the View class that contains a single callback method. These methods will be called by the Android framework when the View to which the listener has been registered is triggered by user interaction with the item in the UI.<br>
1. steps:
     * hardware detects the touch
     * informs View about the event.
     * performs callback method of registered listeners. 

<img src="listener.PNG" width=500 height=300/>

```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        TextView numbers=findViewById(R.id.numbers);
        TextView colors=findViewById(R.id.colors);
        TextView familyMember=findViewById(R.id.family_members);
        TextView phrases=findViewById(R.id.phrases);
        
        // listener objects

        NumbersOnClickListener numbersOnClickListener=new NumbersOnClickListener();
        ColorsOnClickListener colorsOnClickListener=new ColorsOnClickListener();
        FamilyMembersOnClickListener familyMembersOnClickListener=new FamilyMembersOnClickListener();
        PhrasesOnClickListener phrasesOnClickListener=new PhrasesOnClickListener();

       //registering listener objects to View
        numbers.setOnClickListener(numbersOnClickListener);
        colors.setOnClickListener(colorsOnClickListener);
        familyMember.setOnClickListener(familyMembersOnClickListener);
        phrases.setOnClickListener(phrasesOnClickListener);
    }

    public class NumbersOnClickListener implements View.OnClickListener
    {
        @Override
        public void onClick(View v) {
            Intent intent=NumbersActivity.makeNumbersActivityIntent(MainActivity.this); // factory method
            startActivity(intent);
        }
    }

    public class ColorsOnClickListener implements View.OnClickListener
    {
        @Override
        public void onClick(View v) {
            Intent intent=ColorsActivity.makeColorsActivityIntent(MainActivity.this); // factory method
            startActivity(intent);
        }
    }

    public class FamilyMembersOnClickListener implements View.OnClickListener
    {
        @Override
        public void onClick(View v) {
            Intent intent=FamilyMembersActivity.makeFamilyMembersActivityIntent(MainActivity.this); // factory method
            startActivity(intent);
        }
    }

    public class PhrasesOnClickListener implements View.OnClickListener
    {
        @Override
        public void onClick(View v) {
            Intent intent=PhrasesActivity.makePhrasesActivityIntent(MainActivity.this); // factory method
            startActivity(intent);
        }
    }
}
```
### or, short way to write above code 

```java
 protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        TextView numbers=findViewById(R.id.numbers);
        TextView colors=findViewById(R.id.colors);
        TextView familyMember=findViewById(R.id.family_members);
        TextView phrases=findViewById(R.id.phrases);
        

        numbers.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent=NumbersActivity.makeNumbersActivityIntent(MainActivity.this);
                startActivity(intent);
            }
        });
        colors.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                Intent intent=ColorsActivity.makeColorsActivityIntent(MainActivity.this);
                startActivity(intent);

            }
        });
        familyMember.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent=FamilyMembersActivity.makeFamilyMembersActivityIntent(MainActivity.this);
                startActivity(intent);

            }
        });
        phrases.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent=PhrasesActivity.makePhrasesActivityIntent(MainActivity.this);
                startActivity(intent);

            }
        });
    }
  ```
  
  
## OnClickListener vs onClick
When you define a listener using the onClick attribute, the view looks for a method with that name only in its host activity. Programmatically setting an OnClickListener allows you to control a button's behavior from somewhere other than its host activity. This will become very relevant when we learn about Fragments, which are basically mini activities, allowing you to build reusable collections of views with their own lifecycle, which can then be assembled into activities. Fragments always need to use OnClickListeners to control their buttons, since they're not Activities, and won't be searched for listeners defined in onClick.

### creating Miwok application 
<img src="miwoksc1.png" width=200 height=400/>



