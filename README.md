# MathJaxView
[![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)
[![Download](https://api.bintray.com/packages/sidvenu/maven/MathJaxView/images/download.svg)](https://bintray.com/sidvenu/maven/MathJaxView/_latestVersion)

MathJaxView is a custom view extending WebView and offers offline support for MathJax that renders faster than
[MathView] with its support for fast-preview.

<img src="https://github.com/sidvenu/MathJaxView/blob/master/screenshots/screenshot.gif">

## Setup
You can add MathJaxView to your Android Studio project in two ways:
1. Using a remote Maven repository (jCenter)
1. Using AAR file downloaded from bintray
### 1. Setup from a remote Maven repository (jcenter)

Add `implementation 'io.github.sidvenu.mathjaxview:mathjaxview:1.0.5'` into **dependencies** section of your **module** build.gradle file. For example:

```groovy
dependencies {
    implementation fileTree(include: ['*.jar'], dir: 'libs')
    implementation 'com.android.support:appcompat-v7:23.0.0'
    implementation 'io.github.sidvenu.mathjaxview:mathjaxview:1.0.5'
}
```

### 2. Setup from local .aar file

You can download the latest version of MathView from [Bintray].

1) Import the module from local .aar file

Click `File - New - New Module` (yes, not `Import Module`) `-> Import .JAR/.AAR Package`, and find out where the file located.

2) Add dependency

Click `File -> Project Structure -> Dependencies`, and then click the plus icon, select `3. Module Dependency`.

## Usage
The usage of MathJaxView is similar to that of TextView

##### XML
```xml
<io.github.sidvenu.mathjaxview.MathJaxView
    android:id="@+id/formula"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="$$2^x=15$$"/>
```

##### Java
```java
public class MainActivity extends AppCompatActivity {
    MathJaxView view;
    String tex = "Inline formula:" +
            " $ax^2 + bx + c = 0$" +
            "or displayed formula: $$\\sum_{i=0}^n i^2 = \\frac{(n^2+n)(2n+1)}{6}$$";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    protected void onResume() {
        super.onResume();

        view = findViewById(R.id.formula);
        view.setText(tex);
    }
}
```

##### MathJax configuration
The default config is set to use single dollar symbols ($) for inline formula and double dollar symbols ($$) for
displayed formula. You can use the `view.setConfig(String)` method to change the configuration to anything of your
choice.

## Documentation
The code of MathJaxView (a single small file) is well documented and anyone can easily understand it.
Please view the [code]
and try to understand it yourself. If you don't, please raise a issue with the **help wanted** label.

## Issues
Please [report] any issues that you encountered, not limited to performance improvements and
updating the MathJax assets.

## Pull Requests
PRs are an all-time welcome provided you follow the coding style similar to that already existing in the project.

## Thanks
A sincere thanks to [kexanie] for their [MathView] project
that served as an inspiration for this project.

## License
This software is licensed under the Apache License, Version 2.0. Refer the [license] for more details.

[MathView]: https://github.com/kexanie/MathView
[Bintray]: https://bintray.com/sidvenu/maven/MathJaxView/_latestVersion
[code]: https://github.com/sidvenu/MathJaxView/blob/master/mathjaxview/src/main/java/io/github/sidvenu/mathjaxview/MathJaxView.java
[report]: https://github.com/sidvenu/MathJaxView/issues
[kexanie]: https://github.com/kexanie
[license]: https://github.com/sidvenu/MathJaxView/blob/master/LICENSE.md