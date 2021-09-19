# Polishing Views
1.  
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"-----> otherwise, wrap the content
    android:orientation="horizontal"
    android:minHeight="88dp"----------------> min height

    >
```
2. View.setVisibility(View.VISIBLE | View.Invisible | View.GONE);
      * `View.VISIBLE` :  view is visible to user.
      * `View.INVISIBLE`: view is invisible to the user but using space of the view.
      * `View.GONE` : view is completely gone, invisible + using no space.
3. values/dimens.xml to set dimens just like colors, strings.




