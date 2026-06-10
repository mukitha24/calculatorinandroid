## Ex.No:5 Develop a program to create a simple calculator using Android Studio.
## AIM:
To develop a program to create a simple calculator using Android Studio.

## EQUIPMENTS REQUIRED:
Android Studio(Latest Version)

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as Calculativour and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
## MainActivity.java
```
package com.example.calculatorapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    private EditText editText;
    private TextView resultText;
    private Button addButton, subtractButton, multiplyButton, divideButton, equalButton, clearButton;
    private Button num1Button, num2Button, num3Button, num4Button;
    private Button num5Button, num6Button, num7Button, num8Button, num9Button, zeroButton, dotButton;
    private double num1, num2;
    private boolean isAddition, isSubtraction, isMultiplication, isDivision;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText2);
        resultText = findViewById(R.id.resultText);
        clearButton = findViewById(R.id.clear_text);


        addButton = findViewById(R.id.add);
        subtractButton = findViewById(R.id.sub);
        multiplyButton = findViewById(R.id.mul);
        divideButton = findViewById(R.id.div);
        equalButton = findViewById(R.id.submit);

        num1Button = findViewById(R.id.num1);
        num2Button = findViewById(R.id.num2);
        num3Button = findViewById(R.id.num3);
        num4Button = findViewById(R.id.num4);
        num5Button = findViewById(R.id.num5);
        num6Button = findViewById(R.id.num6);
        num7Button = findViewById(R.id.num7);
        num8Button = findViewById(R.id.num8);
        num9Button = findViewById(R.id.num9);
        zeroButton = findViewById(R.id.zero);
        dotButton = findViewById(R.id.dot);

        addButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (editText.getText().length() > 0) {
                    num1 = Double.parseDouble(editText.getText().toString());
                    isAddition = true;

                    // Clear the EditText for the next number
                    editText.setText("");
                }
            }
        });

        subtractButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (editText.getText().length() > 0) {
                    num1 = Double.parseDouble(editText.getText().toString());
                    isSubtraction = true;

                    // Clear the EditText for the next number
                    editText.setText("");
                }
            }
        });

        multiplyButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (editText.getText().length() > 0) {
                    num1 = Double.parseDouble(editText.getText().toString());
                    isMultiplication = true;

                    // Clear the EditText for the next number
                    editText.setText("");
                }
            }
        });

        divideButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (editText.getText().length() > 0) {
                    num1 = Double.parseDouble(editText.getText().toString());
                    isDivision = true;

                    // Clear the EditText for the next number
                    editText.setText("");
                }
            }
        });

        clearButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText("");
                resultText.setText("0");
                // Reset all flags
                isAddition = false;
                isSubtraction = false;
                isMultiplication = false;
                isDivision = false;
            }
        });

        equalButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (editText.getText().length() > 0) {
                    num2 = Double.parseDouble(editText.getText().toString());
                    if (isAddition) {
                        resultText.setText(String.valueOf(num1 + num2));
                    } else if (isSubtraction) {
                        resultText.setText(String.valueOf(num1 - num2));
                    } else if (isMultiplication) {
                        resultText.setText(String.valueOf(num1 * num2));
                    } else if (isDivision) {
                        if (num2 != 0) {
                            resultText.setText(String.valueOf(num1 / num2));
                        } else {
                            resultText.setText("Error");
                        }
                    }
                    // Reset all flags
                    isAddition = false;
                    isSubtraction = false;
                    isMultiplication = false;
                    isDivision = false;
                }
            }
        });

        num1Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "1");
            }
        });

        num2Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "2");
            }
        });

        num3Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "3");
            }
        });

        num4Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "4");
            }
        });

        num5Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "5");
            }
        });

        num6Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "6");
            }
        });

        num7Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "7");
            }
        });

        num8Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "8");
            }
        });

        num9Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "9");
            }
        });

        zeroButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editText.setText(editText.getText().toString() + "0");
            }
        });

        dotButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (!editText.getText().toString().contains(".")) {
                    editText.setText(editText.getText().toString() + ".");
                }
            }
        });
    }
}
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#F5F5F0"
    android:gravity="center"
    android:padding="24dp">

    <!-- Display -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:background="#FFFFFF"
        android:padding="20dp"
        android:layout_marginBottom="12dp">

        <EditText
            android:id="@+id/editText2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textAlignment="textEnd"
            android:focusable="false"
            android:focusableInTouchMode="false"
            android:textSize="28sp"
            android:textColor="#1A1A1A"
            android:hint="0"
            android:textColorHint="#BBBBBB"
            android:background="@null"
            android:paddingBottom="8dp" />

        <View
            android:layout_width="match_parent"
            android:layout_height="1dp"
            android:background="#EBEBEB" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:gravity="end"
            android:paddingTop="8dp">

            <TextView
                android:id="@+id/result"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:textSize="14sp"
                android:textColor="#999999"
                android:text="Result: " />

            <TextView
                android:id="@+id/resultText"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:textSize="14sp"
                android:textColor="#1A1A1A"
                android:textStyle="bold"
                android:text="0" />
        </LinearLayout>
    </LinearLayout>

    <!-- Button Grid -->
    <TableLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:shrinkColumns="*"
        android:stretchColumns="*">

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:id="@+id/num1"
                style="@style/CalcNumButton"
                android:text="1" />

            <Button
                android:id="@+id/num2"
                style="@style/CalcNumButton"
                android:text="2" />

            <Button
                android:id="@+id/num3"
                style="@style/CalcNumButton"
                android:text="3" />

            <Button
                android:id="@+id/add"
                style="@style/CalcOpButton"
                android:text="+" />
        </TableRow>

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:id="@+id/num4"
                style="@style/CalcNumButton"
                android:text="4" />

            <Button
                android:id="@+id/num5"
                style="@style/CalcNumButton"
                android:text="5" />

            <Button
                android:id="@+id/num6"
                style="@style/CalcNumButton"
                android:text="6" />

            <Button
                android:id="@+id/sub"
                style="@style/CalcOpButton"
                android:text="−" />
        </TableRow>

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:id="@+id/num7"
                style="@style/CalcNumButton"
                android:text="7" />

            <Button
                android:id="@+id/num8"
                style="@style/CalcNumButton"
                android:text="8" />

            <Button
                android:id="@+id/num9"
                style="@style/CalcNumButton"
                android:text="9" />

            <Button
                android:id="@+id/mul"
                style="@style/CalcOpButton"
                android:text="×" />
        </TableRow>

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:id="@+id/dot"
                style="@style/CalcOpButton"
                android:text="." />

            <Button
                android:id="@+id/zero"
                style="@style/CalcNumButton"
                android:text="0" />

            <Button
                android:id="@+id/clear_text"
                style="@style/CalcOpButton"
                android:text="CE" />

            <Button
                android:id="@+id/div"
                style="@style/CalcOpButton"
                android:text="÷" />
        </TableRow>

    </TableLayout>

    <Button
        android:id="@+id/submit"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:backgroundTint="#EF9F27"
        android:textColor="#412402"
        android:textSize="15sp"
        android:textStyle="bold"
        android:text="Submit"
        android:paddingTop="14dp"
        android:paddingBottom="14dp" />

</LinearLayout>
```
### styles.xml
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="CalcNumButton">
        <item name="android:layout_width">wrap_content</item>
        <item name="android:layout_height">wrap_content</item>
        <item name="android:layout_margin">4dp</item>
        <item name="android:paddingTop">16dp</item>
        <item name="android:paddingBottom">16dp</item>
        <item name="android:paddingStart">20dp</item>
        <item name="android:paddingEnd">20dp</item>
        <item name="android:backgroundTint">#FAC775</item>
        <item name="android:textColor">#412402</item>
        <item name="android:textSize">16sp</item>
        <item name="android:textStyle">bold</item>
    </style>

    <style name="CalcOpButton">
        <item name="android:layout_width">wrap_content</item>
        <item name="android:layout_height">wrap_content</item>
        <item name="android:layout_margin">4dp</item>
        <item name="android:paddingTop">16dp</item>
        <item name="android:paddingBottom">16dp</item>
        <item name="android:paddingStart">20dp</item>
        <item name="android:paddingEnd">20dp</item>
        <item name="android:backgroundTint">#FFFFFF</item>
        <item name="android:textColor">#1A1A1A</item>
        <item name="android:textSize">16sp</item>
        <item name="android:textStyle">bold</item>
    </style>
</resources>
```
## OUTPUT
<img width="1200" height="2541" alt="image" src="https://github.com/user-attachments/assets/b1f1a4f8-c2c3-409b-9bb0-494086c7baf9" />

## RESULT
Thus a Simple Calculator Application using Android Studio is developed and executed successfully
