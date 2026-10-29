Develop an Android application using FrameLayout to overlay UI elements.
← Back to Index
c) Develop an Android application using FrameLayout to overlay UI elements.
Project Name : FrameLayout
I Filename: activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:id="@+id/main"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <ImageView
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:contentDescription="Background star"
 android:scaleType="centerInside"
 android:src="@android:drawable/btn_star_big_on" />
 <TextView
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_gravity="center"
 android:gravity="center"
 android:text="Welcome to FrameLayout"
 android:textSize="24sp"
 android:textStyle="bold" />
 <Button
 android:id="@+id/button"# Develop an Android Application Using FrameLayout to Overlay UI Elements

## Project Name: `FrameLayout`

## Aim

To develop an Android application using `FrameLayout` to overlay multiple UI elements, including an ImageView, TextView, and Button, on top of one another.

## Technologies Used

- **Programming Language:** Java
- **IDE:** Android Studio
- **Layout:** FrameLayout
- **UI Design:** XML
- **Toast Message:** Android Toast

## Project Structure

```text
FrameLayout/
├── app/
│   └── src/
│       └── main/
│           ├── java/
│           │   └── com/
│           │       └── example/
│           │           └── framelayout/
│           │               └── MainActivity.java
│           ├── res/
│           │   └── layout/
│           │       └── activity_main.xml
│           └── AndroidManifest.xml
└── README.md
```

---

## 1. `activity_main.xml`

**Location:** `app/src/main/res/layout/activity_main.xml`

This XML file uses `FrameLayout` to position an ImageView as the background, a TextView in the center, and a Button at the bottom of the screen.

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:contentDescription="Background star"
        android:scaleType="centerInside"
        android:src="@android:drawable/btn_star_big_on" />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:gravity="center"
        android:text="Welcome to FrameLayout"
        android:textSize="24sp"
        android:textStyle="bold" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|center_horizontal"
        android:layout_marginBottom="24dp"
        android:text="Click here" />

</FrameLayout>
```

---

## 2. `MainActivity.java`

**Location:** `app/src/main/java/com/example/framelayout/MainActivity.java`

This Java file initializes the layout and handles the button click event. When the user clicks the button, a Toast message appears.

```java
package com.example.framelayout;

import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button button = findViewById(R.id.button);

        button.setOnClickListener(v ->
            Toast.makeText(
                this,
                "Button clicked",
                Toast.LENGTH_SHORT
            ).show()
        );
    }
}
```

---

## 3. `AndroidManifest.xml`

**Location:** `app/src/main/AndroidManifest.xml`

Ensure that `MainActivity` is declared as the launcher activity.

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <application
        android:allowBackup="true"
        android:label="FrameLayout"
        android:supportsRtl="true"
        android:theme="@style/Theme.FrameLayout">

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>
```

**Note:** Make sure `@style/Theme.FrameLayout` matches the theme name in your Android Studio project. Keep your existing theme reference if it differs.

---

## 4. How to Run the Application

1. Open Android Studio.
2. Create a new Android project named `FrameLayout`.
3. Select **Java** as the programming language.
4. Set the package name to `com.example.framelayout`.
5. Open `activity_main.xml` and paste the XML code provided above.
6. Open `MainActivity.java` and paste the Java code provided above.
7. Verify that the activity and theme are configured correctly in `AndroidManifest.xml`.
8. Run the application on an emulator or Android device.
9. Observe the star image, centered welcome message, and bottom button.
10. Click the **Click here** button to display the Toast message.

---

## 5. Expected Output

### Application Screen

The application displays the following elements:

- A star image in the background.
- The text **Welcome to FrameLayout** in the center.
- A **Click here** button at the bottom.

```text
+--------------------------------------+
|                                      |
|                                      |
|              ★                       |
|                                      |
|       Welcome to FrameLayout         |
|                                      |
|                                      |
|                                      |
|           [ Click here ]             |
|                                      |
+--------------------------------------+
```

*Illustrative representation of the screen layout.*

### Button Click Output

When the user clicks the button, the following Toast message appears:

```text
Button clicked
```

---

## 6. Working of the Application

1. The application starts and loads `activity_main.xml`.
2. The `FrameLayout` acts as a container for multiple UI elements.
3. The ImageView displays the star image.
4. The TextView overlays the image and displays the welcome message in the center.
5. The Button is positioned at the bottom center of the screen.
6. When the button is clicked, the application displays a Toast message.

### Layout Hierarchy

```text
FrameLayout
    |
    |-- ImageView
    |      Background star image
    |
    |-- TextView
    |      Centered welcome message
    |
    |-- Button
           Bottom-centered button
```

In a `FrameLayout`, child views are drawn in the order they appear in the XML file. Later views are drawn above earlier views when their positions overlap.

---

## 7. Key Concepts

- **FrameLayout:** A layout container used to stack or overlay UI elements.
- **ImageView:** Displays an image or drawable resource.
- **TextView:** Displays text on the screen.
- **Button:** Allows users to perform an action.
- **`layout_gravity`:** Controls the position of a child view inside its parent.
- **`gravity`:** Controls the positioning of content inside a view.
- **`setOnClickListener()`:** Handles button click events.
- **Toast:** Displays a short message to the user.

---

## 8. Result

Thus, an Android application using `FrameLayout` to overlay UI elements was developed successfully. The application displays a background star image, a centered welcome message, and a button at the bottom. Clicking the button displays a Toast message.


 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:layout_gravity="bottom|center_horizontal"
 android:layout_marginBottom="24dp"
 android:text="Click here" />
</FrameLayout>
II Filename: main_activity.java
package com.example.framelayout;
import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 Button button = findViewById(R.id.button);
 button.setOnClickListener(v -> Toast.makeText(this, "Button clicked",
Toast.LENGTH_SHORT).show());
 }
}
