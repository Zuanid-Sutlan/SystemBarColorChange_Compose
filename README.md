
# Change System Bar Colors in Compose

The SystemBar color change code is no longer working in the latest Android Studio version 2024.1.1 

Here is the code to change the SystemBar color from the Theme file in the jetpack compose app.

if you are using enableEdgeToEdge() then non-of-these are needed



## Deployment

Paste the following Code in package_name\ui\Theme.kt

```bash
  val view = LocalView.current
    if (!view.isInEditMode) {
        SideEffect {
            val window = (view.context as Activity).window
            window.statusBarColor = Color.Transparent.toArgb() // this is for status bar color
            window.navigationBarColor = Color.Transparent.toArgb() //this is for bottom system navigation bar color
            WindowCompat.getInsetsController(window, view).isAppearanceLightStatusBars = false // this is for status bar text color
        }
    }
```

## Deployment
Below is another way to do the same 

```bash
    val view = LocalView.current
    if (!view.isInEditMode){
        SideEffect {
            val window = (view.context as Activity).window
            window.statusBarColor = Color.Transparent.toArgb()
            val wic = WindowCompat.getInsetsController(window, view)
            wic.isAppearanceLightStatusBars = !darkTheme
            wic.isAppearanceLightNavigationBars = !darkTheme
        }
    }
```

    
