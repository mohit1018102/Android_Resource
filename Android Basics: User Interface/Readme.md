# Building Layout : part 1
**vocabulary Glossary: https://developers.google.com/android/for-all/vocab-words/?utm_source=udacity&utm_medium=course&utm_campaign=android_basics**<br>
**color:https://material.io/design/color/the-color-system.html**<br>
**typography :https://material.io/design/typography/the-type-system.html**<br>

### Learn about
a.) dp(density independent pixels) : used with views<br>
b.) sp(scale independent pixels): used with text <br>
c.) views, ImageView : src, **scaleType->center,centerCrop** ,TextView   :(common layout_width, layout_height)<br>
d.) wrap_content

# Building Layout part 2:
### Learn about
a.) ViewGroups : LinearLayout: orientation->(vertical/horizontal), layout_weight=1(to distribute equal width or height *set 0dp resp*)<br>
b.) xmlns: android --> signifies **android:** text is an android attributes<br>
c.) RelativeLayout : child views attributes -> 
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
*used by relativelayout to position child views*<br>

