# Android Customize Library
This library let you do the following things very easy
- add a preference to let the user choose his favourite theme
- apply the theme to your activity
- Custom toolbar
- change the color of the status bar

## Availbale themes
- blue
- yellow
- green
- red
- dark
- light

## Available colors
To use in xml:
- colorPrimary
- colorPrimaryDark
- colorAccent
- colorPrimaryLight
- colorFont
- colorFontDisabled
- colorSecondFont
- colorIconsToolbar
- colorBackground
- colorSecondBackground
- colorWindowsBackground

To use programatically:
- Colors.PRIMARY
- Colors.PRIMARY_DARK
- Colors.PRIMARY_LIGHT
- Colors.ACCENT
- Colors.FONT
- Colors.FONT_DISABLED
- Colors.SECOND_FONT
- Colors.ICONS_TOOLBAR
- Colors.BACKGROUND
- Colors.SECOND_BACKGROUND
- Colors.WINDOWS_BACKGROUND

I will add new colors and themes when you start a pull request.

## Usage
### Preference
Add the preference into the xml file for your preference   

    <schalter.dev.customizelibrary.DesignPref
        android:key="color_custom_design"
        android:title="@string/pref_custom_color"
        android:defaultValue="2" 
        />
        
Values for **android:defaultValue**:
- 0: Blue
- 1: Yellow
- 2: Green
- 3: Red
- 4: Dark
- 5: Light

### Custom Toolbar
Add the custom toolbar to your xml-Layout   

    <schalter.dev.customizelibrary.CustomToolbar
       android:id="@+id/toolbar"
       ...
    />
    
Get the toolbar and do what you want (it extends from Google Support Toolbar)   

    CustomToolbar toolbar = (CustomToolbar) findViewById(R.id.toolbar);
    toolbar.setTitle("Title");
    toolbar.setItemColor(Color.GREEN); // set the color of the font and icons
    
    // If you are in AppCompatActivity you can do (does work for all toolbars)
    setSupportActionBar(toolbar);
    
### Custom Theme
Add this to your onCreate in every Activity   

    setTheme(Colors.getTheme(this)); //this is the actvity
    // this will set the theme to the theme choosed in the preferences
    
### Status Bar Color
To change the status bar color use this   

    Colors.setStatusBarColor(this, Colors.PRIMARYDARK);
    
### Get Colors for the right themes
To get for example the primary color   

    Colors.getColor(context, Colors.PRIMARY);
    
**never just use Colors.PRIMARY as your color**
    
In xml files you can use

    ?colorPrimary
    
To set the background of an object add this to the object

    android:background="?colorPrimary"
    
