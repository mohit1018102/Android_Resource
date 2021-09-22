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


# Activity LifeCycle and Audio playback
<img src="img/mediaplayer.PNG"/>

1. ListView provides a single ItemClickListener to process onClick action on views.
    * One way to process onClick is by creating listener for each views (but, if there are ~1000000 rows then this is not an efficient solution). 

```java

listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                stop();

                mMediaPlayer= MediaPlayer.create(FamilyMembersActivity.this,words.get(position).getmAudioMedia());
                mMediaPlayer.setOnCompletionListener(new MediaPlayer.OnCompletionListener() {
                    @Override
                    public void onCompletion(MediaPlayer mp) {
                        stop();
                    }
                });
                mMediaPlayer.start(); //no need to call prepare(); create does that for you
            }
        });
    ....
    
    public void stop() {
        if (mMediaPlayer != null) {

            mMediaPlayer.release();
            mMediaPlayer = null;
        }
    }
}

```




