# Building Layout : part 1
**vocabulary Glossary: https://developers.google.com/android/for-all/vocab-words/?utm_source=udacity&utm_medium=course&utm_campaign=android_basics**<br>
**color:https://material.io/design/color/the-color-system.html**<br>
**typography :https://material.io/design/typography/the-type-system.html**<br>

### Learn about
a.) dp(density independent pixels) : used with views<br>
b.) sp(scale independent pixels): used with text <br>
c.) views, ImageView : src, **scaleType->center,centerCrop** ,TextView   :(common layout_width, layout_height)<br>
d.) wrap_content

# Building Layout : part 2
### Learn about
a.) ViewGroups : LinearLayout: orientation->(vertical/horizontal), layout_weight=1(to distribute equal width or height *set 0dp resp*)<br>
b.) xmlns: android --> signifies **android:** text is an android attributes<br>
c.) RelativeLayout : child views attributes -><br> **layout_xyz:** *used by relative layout to position child views*
<ol type='1'>
      <li> layout_alignParentTop,</li>
      <li> layout_alignParentBottom,</li>
      <li> layout_alignParentLeft, </li>
      <li> layout_alignParentRight, <br>
       <li> layout_centerVertical,<br>
      <li> layout_centerHorizontal,<br>
      <li> layout_centerInParent<br>
  <li> <b>relative to others : @ + resourcetype  refers to resource in android app</b> resourcetype eg:id +(symbol is used when we declare for 1st time)</li>
   <ul>
    <li>layout_toLeftOf= @id/ view_id</li>
    <li>layout_toRightOf= @id/ view_id</li>
    <li>layout_above= @id/ view_id</li>
    <li>layout_below= @id/ view_id</li>
    </ul>
  <li> Padding : manage spacing inside view  <b>android:padding =</b> </li>
  <li> Margin : manage  spacing outside view <b>android:layout_margin=</b> </li>
 </ol>
 
 # Practice Set : Building Layouts

1. Troubleshooting Document: https://docs.google.com/document/d/1w1Xn_hnSAODAAtdRDp7haYPBtEwX_l7Htpf8Wpgbu6w/pub?embedded=true is a growing document that lists solutions to common problems that students run in to.
2. setup JDK + Android studio. 
3. select unique package name com.package.xyz.app .
4. Select minimum SDK : **why not to choose Android 1.0 to support all the versions ?**
      * *because features like NFC ( required hardware) which was not supported by earlier versions.* 
5. Step for creating single screen activity : layout part
      * Select the views<br>
            a. ViewGroup : Relative Layout<br>
            b. TextView : for text<br>
            c. ImageView: for image<br>
      * Position the Views *(ViewGroup is also a view)*
      * Style the views
 6. Save image inside res/drawable : for <code> android: src="@drawable/cake" </code>
 ## CODE : https://github.com/udacity/Happy-Birthday   
 
 7. If you’re curious about the road even farther ahead, these are the free courses that make up the Android Basics Nanodegree:
       * Android Basics: User Interface (this course) : 
       * Android Basics: User Input :
       * Android Basics: Multiple App Screens
       * Android Basics: Networking
       * Android Basics: Data Storage
 8. Here are some of Kirill’s favorite Android resources:

      * <a href="https://blog.stylingandroid.com/">Styling Android blog:</a> A blog that shows off various technical aspects of building design elements of Android apps.
      * <a href="https://chris.banes.dev/">Chris Banes' blog:</a> A blog that gives you a deeper look into Android support libraries.
      * <a href="https://fragmentedpodcast.com/">Fragmented Podcast:</a> A weekly podcast filled with Android development discussion.



