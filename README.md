# Android Toolbar
First you must know default android material design check image below from android develper page
![](http://developer.android.com/training/material/images/ThemeColors.png)

## Create your custom Toolbar
* Create new android project by default will create the below toolbar
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/1.png)
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/2.png)
```Java
<android.support.v7.widget.Toolbar
    android:id="@+id/toolbar"
    android:layout_width="match_parent"
    android:layout_height="?attr/actionBarSize"
    android:background="?attr/colorPrimary"
    app:popupTheme="@style/AppTheme.PopupOverlay" />
```
* Change the background color (colorPrimary)
Under values -> colors.xml 
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/3.png)

change colorPrimary 
```Java
From
<color name="colorPrimary">#3F51B5</color>
To 
<color name="colorPrimary">#aa3939</color>
```
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/4.png)
* Change toolbar background to image 
change android:background to your drawable file
```Java
android:background="?attr/colorPrimary"
```
* Change the status bar background color change 
```Java
From
<color name="colorPrimaryDark">#303F9F</color>
To
<color name="colorPrimaryDark">#550000</color>
```
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/5.png)
* Change the status bar background To image or gradient color

We cant change it direct but to do that you need to set colorPrimaryDark to transparent 
```Java
<color name="colorPrimaryDark">#0000</color>
```
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/6.png)

Then set background to “CoordinatorLayout” At “activity_main.xml”
 ```Java
 <?xml version="1.0" encoding="utf-8"?>
<android.support.design.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    android:background="@drawable/coordinator_layout_bg"
    tools:context=".MainActivity">

    <android.support.design.widget.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:theme="@style/AppTheme.AppBarOverlay">

        <android.support.v7.widget.Toolbar
            android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?attr/actionBarSize"
            android:background="?attr/colorPrimary"
            app:popupTheme="@style/AppTheme.PopupOverlay" />

    </android.support.design.widget.AppBarLayout>

    <include layout="@layout/content_main" />

</android.support.design.widget.CoordinatorLayout>
```

The final output

![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/7.png)

## Create Custom Menu
* Change menu position 

From 

![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/8.png)

To

![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/9.png)

By default display menu over toolbar is the new android metrical design 

Open your values/style.xml and add overflowmenu style to your AppTheme

For before Lollipop
```Java
<!-- Base application theme. -->
<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    <!-- Customize your theme here. -->
    <item name="colorPrimary">@color/colorPrimary</item>
    <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
    <item name="colorAccent">@color/colorAccent</item>
    <item name="actionOverflowMenuStyle">@style/overFlowMenyStyle</item>
</style>
<style name="overFlowMenyStyle" parent="Widget.AppCompat.PopupMenu.Overflow">
    <item name="overlapAnchor">false</item>
    <!--<item name="android:dropDownVerticalOffset">5dp</item>-->
</style>
```
For Lollipop open v21/style.xml 
```Java
<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    <!-- Customize your theme here. -->
    <item name="colorPrimary">@color/colorPrimary</item>
    <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
    <item name="colorAccent">@color/colorAccent</item>
    <item name="actionOverflowMenuStyle">@style/overFlowMenyStyle</item>
</style>
<style name="overFlowMenyStyle" parent="Widget.AppCompat.PopupMenu.Overflow">
    <item name="android:overlapAnchor">false</item>
    <!--<item name="android:dropDownVerticalOffset">5dp</item>-->
</style>
```

* Change menu icon and add icons to menuItems

![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/10.png)

Open your menu_main.xml file

![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/11.png)

Then update the menu like below
```Java
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".MainActivity">
    <item
        android:id="@+id/action_test"
        android:icon="@android:drawable/ic_menu_more"
        android:orderInCategory="1"
        app:showAsAction="always">
        <menu>
            <item
                android:id="@+id/action_settings"
                android:icon="@android:drawable/ic_menu_manage"
                android:title="@string/action_settings" />
        </menu>
    </item>
</menu>
```

## Add icon to toolbar 
open MainActivity.java
```Java
Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
toolbar.setNavigationIcon(R.mipmap.ic_launcher);
setSupportActionBar(toolbar);
```
![](https://github.com/sallySalem/Custom-Toolbar/blob/master/Images/12.png)

## Change Toolbar Title Style
## Change NavigationBarColor 

## License
The MIT License (MIT)

Copyright (c) 2016 sallySalem

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.



