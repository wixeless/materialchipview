

# MaterialChipView

A checkable widget for Android. Based on the [EventFilterView from the Google I/O 2019 app](https://github.com/google/iosched/blob/2696fc7e06826ba2db72de243f0d63f83f4a29b5/mobile/src/main/java/com/google/samples/apps/iosched/ui/schedule/filters/EventFilterView.kt). 

Requires Android `minSdkVersion` 21.

![demo.gif](demo.gif)

## Setup
Make sure you have the jcenter repo in your project level `build.gradle`  
```gradle
allprojects {
    repositories {
        jcenter()
    }
}
```

Add the dependency to your lib/app `build.gradle`  
```gradle
dependencies {
     implementation 'com.github.jahongir28:materialchipview:1.0.0'
}
```

## Usage

### XML
Include the widget into your xml layout like this
```xml
<kg.stark.materialchipview.MaterialChipView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Marvel Stud10s"/>
```

The following xml attributes are supported

| Attribute              | Description                                                                               |    |
|:-----------------------|:------------------------------------------------------------------------------------------|:---|
| `android:text`         | The text to display                                                                       |    |
| `android:textColor`    | The default text color                                                                    |    |
| `android:color`        | The color of the indicator dot as well as the background color when the widget is checked |    |
| `android:background`   | The default background color                                                              |    |
| `android:checked`      | The checked state of the widget, either `true` or `false`                                 |    |
| `app:cornerRadius`     | The corner radius of the outline, in dp. Defaults to a pill shape if not set              |    |
| `app:outlineWidth`     | The stroke width of the outline, in dp                                                    |    |
| `app:checkedTextColor` | The text color when the widget is checked                                                 |    |
| `app:foreground`       | The foreground drawable to display                                                        |    |
| `app:showIcons`        | Show dot icon  `true` or `false`                                                          |    |

### In code
The state of the widget can be observed like this
```kotlin
materialChip.onCheckedChangeListener = { isChecked: Boolean ->
      // do your logic here      
}
```

Starts the animation to enable/disable and invokes a function when done.
```kotlin
materialChip.animateCheckedAndInvoke(checked = true) {
    // onAnimationEnd callback
}
```

Plus, there are following methods at your service for changing the state without animation:
```kotlin
if (!chip.isChecked) {
    chip.isChecked = true
}

chip.toggle() // toggles between states
```

## Acknowledgements
Thanks to the team behind the [Google I/O app](https://github.com/google/iosched). Thank you for open sourcing the code and letting others reuse and learn from it.

## License
    Copyright 2019 Google, Inc.
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.