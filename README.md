GoogleNavigationDrawer
======================

Navigation Drawer Activity with Google design style and simplified methods<br />
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-GoogleNavigationDrawer-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1290)[![Donate](https://www.paypalobjects.com/en_GB/i/btn/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZP25MK8XYDM62)

It requires 14+ API and android support v7 (Toolbar)<br>

[Download example apk](https://raw.github.com/neokree/GoogleNavigationDrawer/master/example.apk)<br>

If you are using GoogleNavigationDrawer in your app and would like to be listed here, please let me know via [email](mailto:neokree@gmail.com)! <br>

### How to add to your project  
In your Activity...
```java
public class MyActivity extends GoogleNavigationDrawer implements GAccountListener {

    @Override
    public void init(Bundle savedInstanceState) {

        // add first account
        GAccount account = new GAccount("NeoKree","neokree@gmail.com",this.getResources().getDrawable(R.drawable.photo),this.getResources().getDrawable(R.drawable.bamboo));
        this.addAccount(account);

        // set listener
        this.setAccountListener(this);

        // add your sections
        this.addSection(this.newSection("Section 1",new FragmentIndex()));
        this.addSection(this.newSection("Section 2",new FragmentIndex()));
        this.addDivisor();
        this.addSection(this.newSection("Recorder",this.getResources().getDrawable(R.drawable.ic_mic_white_24dp),new FragmentIndex()).setNotifications(10));

        // add custom colored section with icon
        this.addSection(this.newSection("Night Section", this.getResources().getDrawable(R.drawable.ic_hotel_grey600_24dp), new FragmentIndex())
                .setSectionColor(Color.parseColor("#2196f3")).setNotifications(150)); // material blue 500

        this.addDivisor();
        // add custom colored section with only text
        this.addSection(this.newSection("Last Section", new FragmentIndex()).setSectionColor((Color.parseColor("#ff9800")))); // material orange 500

        Intent i = new Intent(this,Settings.class);
        this.addSection(this.newSection("Settings",this.getResources().getDrawable(R.drawable.ic_settings_black_24dp),i));

    }

}
```
In your styles.xml choose your version
```xml
<resources>

    <!-- Base application theme. -->
    <style name="AppTheme" parent="GoogleNavigationDrawerTheme">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/light_blue_500</item>
        <item name="colorAccent">@color/grey_1000</item>
    </style>
    <!-- Light version theme. -->
    <style name="AppTheme" parent="GoogleNavigationDrawerTheme.Light">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/light_blue_500</item>
        <item name="colorAccent">@color/grey_1000</item>
    </style>
    <!-- Light version with Black actionbar -->
    <style name="AppTheme" parent="GoogleNavigationDrawerTheme.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/light_blue_500</item>
        <item name="colorAccent">@color/grey_1000</item>
    </style>
    
</resources>
```
N.B. Not override <code>OnCreate</code> method! Use <code>init</code> method instead.<br>

<h3>How to import </h3>
<h6>Android Studio</h6>
Add this to your build.gradle:
```java 
repositories {
    mavenCentral()
}

dependencies {
    compile 'it.neokree:GoogleNavigationDrawer:0.6'
}
```

You don't know how to do something? Visit the [wiki](https://github.com/neokree/GoogleNavigationDrawer/wiki)!

<img src="https://raw.github.com/neokree/GoogleNavigationDrawer/master/screen1.png" alt="screenshot" width="300px" height="auto" />
<img src="https://raw.github.com/neokree/GoogleNavigationDrawer/master/screen2.png" alt="screenshot" width="300px" height="auto" />
 
