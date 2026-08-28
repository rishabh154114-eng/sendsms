
# Ex.No:3 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: T.Rishabh Srivatsav
Registeration Number : 212224113001
*/
```
MainActivity.java
```
package com.example.exp3;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText message, phoneNumber;
    Button send;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        message = findViewById(R.id.editTextText);
        phoneNumber = findViewById(R.id.editTextPhone);
        send = findViewById(R.id.button);

        send.setOnClickListener(v -> sendSMS());
    }

    private void sendSMS() {

        String msg = message.getText().toString();
        String phoneNo = phoneNumber.getText().toString();

        Intent intent = new Intent(Intent.ACTION_SENDTO);
        intent.setData(Uri.parse("smsto:" + phoneNo));
        intent.putExtra("sms_body", msg);

        startActivity(intent);
    }
}
```
Activity.xml
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
        android:id="@+id/editTextText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="24dp"
        android:layout_marginTop="140dp"
        android:layout_marginEnd="24dp"
        android:autofillHints="message"
        android:hint="@string/enter_message"
        android:inputType="textMultiLine"
        android:minHeight="48dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/editTextPhone"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="24dp"
        android:layout_marginTop="12dp"
        android:layout_marginEnd="24dp"
        android:autofillHints="phone_number"
        android:hint="@string/enter_phone_number"
        android:inputType="phone"
        android:minHeight="48dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/editTextText" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="84dp"
        android:text="@string/send_sms"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/editTextPhone" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
String.xml
```
<resources>
    <string name="app_name">My Application</string>
    <string name="hint_enter_message">Enter Message</string>
    <string name="hint_enter_phone">Enter Phone Number</string>
    <string name="btn_send_sms">Send SMS</string>
    <string name="send_sms">Send SMS</string>
    <string name="enter_phone_number">Enter Phone Number</string>
    <string name="enter_message">Enter Message</string>
</resources>
```
## OUTPUT
<img width="1920" height="1080" alt="Screenshot 2026-08-04 101300" src="https://github.com/user-attachments/assets/a1493ddc-1a0a-4299-a644-1c00111d3fbb" />
<img width="1920" height="1080" alt="Screenshot 2026-08-04 101351" src="https://github.com/user-attachments/assets/d7236057-0195-44cd-9c3a-469aa3670f24" />



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
