## Step 1: create anim file

* res/anim/slide_in_right.xml

```bash
<?xml version="1.0" encoding="utf-8"?>

<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="100%p" android:toXDelta="0"
        android:duration="@android:integer/config_mediumAnimTime"/>
</set>
```


* res/anim/slide_out_left.xml

```bash
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="0" android:toXDelta="-100%p"
        android:duration="@android:integer/config_mediumAnimTime"/>
</set>
```

* res/anim/slide_in_left.xml

```bash
<?xml version="1.0" encoding="utf-8"?>

<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="-100%p" android:toXDelta="0"
        android:duration="@android:integer/config_mediumAnimTime"/>
</set>
```

* res/anim/slide_out_right.xml

```bash
<?xml version="1.0" encoding="utf-8"?>

<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="0" android:toXDelta="100%p"
        android:duration="@android:integer/config_mediumAnimTime"/>
</set>
```

## Step 2 : update res/values/styles.xml :

```bash
<!-- Base application theme. -->
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    <!-- Customize your theme here. -->
    <item name="colorPrimary">@color/colorPrimary</item>
    <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
    <item name="colorAccent">@color/colorPrimary</item>
    <item name="android:windowAnimationStyle">@style/CustomActivityAnimation</item>

</style>

<style name="CustomActivityAnimation" parent="@android:style/Animation.Activity">
    <item name="android:activityOpenEnterAnimation">@anim/slide_in_right</item>
    <item name="android:activityOpenExitAnimation">@anim/slide_out_left</item>
    <item name="android:activityCloseEnterAnimation">@anim/slide_in_left</item>
    <item name="android:activityCloseExitAnimation">@anim/slide_out_right</item>
</style>
```