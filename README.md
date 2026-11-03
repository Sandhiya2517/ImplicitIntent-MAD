# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: SANDHIYA M
Registeration Number : 212224220086
*/
```
MainActivity.java
```
package com.example.muidex_2a;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EditText editText = findViewById(R.id.editText);
        Button button = findViewById(R.id.btn);

        button.setOnClickListener(view -> {
            String url = editText.getText().toString().trim();

            if (url.isEmpty()) {
                Toast.makeText(MainActivity.this,
                        "Enter a website URL",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            if (!url.startsWith("https://") && !url.startsWith("http://")) {
                url = "https://" + url;
            }

            Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
            startActivity(intent);
        });
    }
}


```
activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="@string/enter_url"
        android:inputType="textUri"
        android:autofillHints="url"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/btn"
        android:text="@string/search"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText" />


</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT
<img width="1916" height="1198" alt="Screenshot 2026-11-03 084338" src="https://github.com/user-attachments/assets/c5f32ae7-a2af-49da-b3e5-5bdaa3fb6b9f" />

<img width="1916" height="1148" alt="Screenshot 2026-11-03 084458" src="https://github.com/user-attachments/assets/c3d0928d-a713-4a68-af18-e3119e2730e3" />

<img width="1911" height="1141" alt="Screenshot 2026-11-03 084538" src="https://github.com/user-attachments/assets/db88c4cf-2eef-4214-b602-3054b4fc588d" />



## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


