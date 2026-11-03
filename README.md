# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. **Start the project:** Create a new Android project in Android Studio.

2. **Design the UI:** In `activity_main.xml`, add an `EditText` (to accept the URL input) and a `Button` (to trigger the navigation).

3. **Initialize components:** In `MainActivity.java`, map the `EditText` and `Button` variables to their respective XML IDs using `findViewById()`.

4. **Set click listener:** Attach an `OnClickListener` to the button to listen for user click events.

5. **Get input:** Inside the `onClick` method, extract the text entered in the `EditText` and convert it to a string.

6. **Create implicit intent:** Instantiate an `Intent` with the action `Intent.ACTION_VIEW` and pass the parsed URL string using `Uri.parse()`.

7. **Start activity:** Call `startActivity(intent)` to trigger the OS to open the webpage in an available web browser.

8. **Stop:** Run and test the application.

## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:JAYAGANAPATHI S
Registeration Number :212224040133
*/
```
Main Activity.java
```
package com.example.implicity;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.view.View;
import android.widget.EditText;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText);
        button = findViewById(R.id.btn);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String url = editText.getText().toString().trim();

                if (url.isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Enter a website URL",
                            Toast.LENGTH_SHORT).show();
                    return;
                }

                if (!url.startsWith("http://")
                        && !url.startsWith("https://")) {
                    url = "https://" + url;
                }

                Intent intent = new Intent(
                        Intent.ACTION_VIEW,
                        Uri.parse(url)
                );

                startActivity(intent);
            }
        });
    }
}
```

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:hint="Enter website URL"
        android:inputType="textUri"
        android:padding="12dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.4"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.122" />

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="368dp"
        android:onClick="search"
        android:text="Open Website"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT
<img width="1440" height="900" alt="Screenshot 2026-11-03 at 9 05 37 AM" src="https://github.com/user-attachments/assets/08c1087e-6867-4d9a-b885-368f105d082d" />
<img width="1440" height="900" alt="Screenshot 2026-11-03 at 9 08 21 AM" src="https://github.com/user-attachments/assets/6140205d-a9c7-4821-b5c2-fd3be8c5629d" />
<img width="1440" height="900" alt="Screenshot 2026-11-03 at 9 06 10 AM" src="https://github.com/user-attachments/assets/e8891e74-35bf-452e-9951-f9204854ff44" />
<img width="1440" height="900" alt="Screenshot 2026-11-03 at 9 14 51 AM" src="https://github.com/user-attachments/assets/bcb60abf-6d4c-4429-8911-14344d96500b" />
<img width="1440" height="900" alt="Screenshot 2026-11-03 at 9 15 00 AM" src="https://github.com/user-attachments/assets/c30d5dfb-b8c1-40c7-9167-e057d25cbd54" />

## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


