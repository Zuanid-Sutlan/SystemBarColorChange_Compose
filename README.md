
# Change System Bar Colors in Compose

The SystemBar color change code is no longer working in the latest Android Studio version 2024.1.1 

Here is the code to change the SystemBar color from the Theme file in the jetpack compose app.



## Deployment

Paste the following Code in package_name\ui\Theme.kt

```bash
  val view = LocalView.current
    if (!view.isInEditMode) {
        SideEffect {
            val window = (view.context as Activity).window
            window.statusBarColor = Color.Transparent.toArgb()
            window.navigationBarColor = Color.Transparent.toArgb() //if (Prefs.isDarkTheme) Color.Black.toArgb() else Color.White.toArgb()
            WindowCompat.getInsetsController(window, view).isAppearanceLightStatusBars = false
        }
    }
```


    
