## update color: res/values/color.xml

```bash
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="color_primary">#2196F3</color>
    <color name="color_primary_dark">#1976D2</color>
    <color name="accent_color">#536DFE</color>
</resources>
```



## update style: res/values/styles.xml

```bash
<resources>
    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/color_primary</item>
        <item name="colorPrimaryDark">@color/color_primary_dark</item>
        <item name="colorAccent">@color/accent_color</item>
    </style>
</resources>
```



## update string: res/values/strings.xml

```bash
<resources>
    <string name="app_name">Android Toolbar</string>
    <string name="action_settings">Settings</string>
    <string name="action_refresh">Settings</string>
    <string name="action_new">Settings</string>
    <string name="logo_desc">App logo</string>
</resources>
```



## add toolbar: activity_main.xml

```bash
<android.support.v7.widget.Toolbar
        android:id="@+id/toolbar"
        android:minHeight="?attr/actionBarSize"
        android:background="@color/color_primary"
        android:layout_width="match_parent"
        android:layout_height="64dp">
</android.support.v7.widget.Toolbar>
```



## create menu: res/menu/menu_main.xml
```bash
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".MainActivity">
    <item android:id="@+id/action_settings"
        android:title="@string/action_settings"
        android:orderInCategory="100"
        app:showAsAction="never" />

    <item
		android:id="@+id/menu_location"
		android:orderInCategory="100"
		android:showAsAction="never"
		android:title="Location" />	
			
	<item
		android:id="@+id/menu_sleep"
		android:orderInCategory="100"
		android:showAsAction="never"
		android:title="Sleep" />    

    <item android:id="@+id/action_refresh"
        android:title="@string/action_refresh"
        android:icon="@drawable/ic_action_refresh"
        android:orderInCategory="200"
        app:showAsAction="ifRoom" />

    <item android:id="@+id/action_new"
        android:title="@string/action_new"
        android:icon="@drawable/ic_action_new"
        android:orderInCategory="300"
        app:showAsAction="ifRoom" />
</menu>

```

## handling interaction: in activity.java

```bash
@Override
    protected void onCreate(Bundle savedInstanceState) {
        //

        setTitle(null);
        Toolbar topToolBar = (Toolbar)findViewById(R.id.toolbar);
        setSupportActionBar(topToolBar);
        topToolBar.setLogo(R.drawable.logo);
        topToolBar.setLogoDescription(getResources().getString(R.string.logo_desc));

       //
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.menu_main, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        int id = item.getItemId();

        //noinspection SimplifiableIfStatement
        if (id == R.id.action_settings) {
            return true;
        }
        if(id == R.id.action_refresh){
            Toast.makeText(Main2Activity.this, "Refresh App", Toast.LENGTH_LONG).show();
        }
        if(id == R.id.action_new){
            Toast.makeText(Main2Activity.this, "Create Text", Toast.LENGTH_LONG).show();
        }
        return super.onOptionsItemSelected(item);
    }
```
    