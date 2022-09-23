
# Ex.No:2b Explicit Intents

Develop program to create two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a layout,click button and display factorial number using Explicit Intents in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min. required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as ExplicitIntent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display factorial number using Explicit Intents in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the text “Explicit Intents”.
Developed by : Kaushika.A
Registeration Number : 212221230048
*/
```
## activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">


    <EditText
        android:id="@+id/editText1"
        android:layout_width="350dp"
        android:layout_height="60dp"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="220dp"
        android:autofillHints=""
        android:autoSizeMaxTextSize="20dp"
        android:hint="@string/enter_a_number"
        android:inputType="number"
        android:textAlignment="center"
        android:textSize="20sp"
        android:textStyle="bold" />

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/editText1"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="50dp"
        android:layout_marginBottom="353dp"
        android:backgroundTint="@color/black"
        android:text="@string/generate" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="34dp"
        android:layout_below="@+id/editText1"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="119dp"
        android:layout_marginTop="-131dp"
        android:layout_marginEnd="116dp"
        android:layout_marginBottom="547dp"
        android:fontFamily="sans-serif-medium"
        android:text="@string/factorial_generator"
        android:textSize="20sp" />

</RelativeLayout>
```
## MainActivity.java
```java
package com.example.explicit_intent;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.content.Intent;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    EditText editText1;
    Button button1;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText1=findViewById(R.id.editText1);
        button1=findViewById(R.id.button1);

        Intent i = new Intent(MainActivity.this,SecondActivity.class);
        button1.setOnClickListener(view -> {
            i.putExtra("number",editText1.getText().toString());
            startActivity(i);
        });
    }
}
```
## second_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".SecondActivity">

    <TextView
        android:id="@+id/textView2"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginStart="50dp"
        android:layout_marginTop="335dp"
        android:layout_marginEnd="50dp"
        android:layout_marginBottom="335dp"
        android:fontFamily="sans-serif-medium"
        android:textAlignment="center"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</RelativeLayout>
```
## SecondActivity.java
```java
package com.example.explicit_intent;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.TextView;

public class SecondActivity extends AppCompatActivity {

    TextView textView2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        Bundle b= getIntent().getExtras();

        int n =Integer.parseInt(b.getString("number"));
        long f=1;

        for(int i=1;i<=n;i++){
            f=f*i;
        }

        textView2=findViewById(R.id.textView2);
        textView2.setText("Factorial of "+n+" is "+f);
    }
}
```
## OUTPUT
![](01.png)

![](02.png)

![](03.png)

## RESULT
Thus a Simple Android Application to display factorial of the same number using Explicit Intents using Android Studio is developed and executed successfully.
