# Calculator_JustinMorales_JeromeMorales_GioGindoy_JanelleOna_FelixLaput-
simple android calculator application that can add, subtract, multiply and divide two(2) numbers. In division, it will not accept if divisor is zero(0).


import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Context;
import android.content.DialogInterface;
import android.os.Bundle;
import android.view.Gravity;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    TextView result;
    EditText number1,number2;
    Button add,subtract,divide,multiply,clear;
    float resultX;
    int num1,num2;
    final Context context=this;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        result = (TextView) findViewById(R.id.textView2);
        number1= (EditText) findViewById(R.id.editTextNumber1);
        number2= (EditText) findViewById(R.id.editTextNumber2);

        add= (Button)findViewById(R.id.add1);
        subtract= (Button)findViewById(R.id.subtract2);
        divide= (Button)findViewById(R.id.divide4);
        multiply=(Button)findViewById(R.id.multiply3);
        clear=(Button)findViewById(R.id.clear);
        AlertDialog.Builder alertDialogBuilder= new AlertDialog.Builder(context);
        add.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                if(number2.length()!=0 && number1.length()!=0){
                    num1= Integer.parseInt(number1.getText().toString());
                    num2= Integer.parseInt(number2.getText().toString());
                    resultX = num1 + num2;
                    result.setText(String.valueOf(resultX));
                }else {
                    alertDialogBuilder.setTitle("Please Complete Input");
                    alertDialogBuilder.setMessage("Click back ").setCancelable(false).setPositiveButton("back", new DialogInterface.OnClickListener() {
                        @Override
                        public void onClick(DialogInterface dialog, int which) {

                        }
                    });
                    AlertDialog alertDialog = alertDialogBuilder.create();
                    alertDialog.show();
                }

            }
        });
        subtract.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                if(number2.length()!=0 && number1.length()!=0){
                    num1= Integer.parseInt(number1.getText().toString());
                    num2= Integer.parseInt(number2.getText().toString());
                    resultX = num1 - num2;
                    result.setText(String.valueOf(resultX));
                }else {
                    alertDialogBuilder.setTitle("Please Complete Input");
                    alertDialogBuilder.setMessage("Click back ! ").setCancelable(false).setPositiveButton("back", new DialogInterface.OnClickListener() {
                        @Override
                        public void onClick(DialogInterface dialog, int which) {

                        }
                    });
                    AlertDialog alertDialog = alertDialogBuilder.create();
                    alertDialog.show();
                }
            }
        });
        multiply.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if(number2.length()!=0 && number1.length()!=0){
                    num1= Integer.parseInt(number1.getText().toString());
                    num2= Integer.parseInt(number2.getText().toString());
                    resultX = num1 * num2;
                    result.setText(String.valueOf(resultX));
                }else {
                    alertDialogBuilder.setTitle("Please Complete Input");
                    alertDialogBuilder.setMessage("Click back ! ").setCancelable(false).setPositiveButton("back", new DialogInterface.OnClickListener() {
                        @Override
                        public void onClick(DialogInterface dialog, int which) {

                        }
                    });
                    AlertDialog alertDialog = alertDialogBuilder.create();
                    alertDialog.show();
                }
            }
        });
        divide.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {


                if(number2.length()!=0 && number1.length()!=0){

                    num1= Integer.parseInt(number1.getText().toString());
                    num2= Integer.parseInt(number2.getText().toString());


                    if(num2==0){
                        alertDialogBuilder.setTitle("can't divide by Zero !");
                        alertDialogBuilder.setMessage("Click back ! ").setCancelable(false).setPositiveButton("back", new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int which) {

                            }
                        });
                        AlertDialog alertDialog= alertDialogBuilder.create();
                        alertDialog.show();


                    }else
                        resultX= num1/num2;
                    result.setText(String.valueOf(resultX));
                }else {
                    alertDialogBuilder.setTitle("Please Complete Input");
                    alertDialogBuilder.setMessage("Click back ! ").setCancelable(false).setPositiveButton("back", new DialogInterface.OnClickListener() {
                        @Override
                        public void onClick(DialogInterface dialog, int which) {

                        }
                    });
                    AlertDialog alertDialog = alertDialogBuilder.create();
                    alertDialog.show();
                }
            }
        });
        clear.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                number1.getText().clear();
                number2.getText().clear();
               result.setText(String.valueOf(0));
            }

        });

    }
}

-------------------------------------  XML  ---------------------------------------------------------
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextNumber1"
        android:hint="enter number"
        android:layout_width="236dp"
        android:layout_height="67dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="90dp"
        android:layout_marginLeft="90dp"
        android:layout_marginTop="26dp"
        android:layout_marginEnd="85dp"
        android:layout_marginRight="85dp"
        android:layout_marginBottom="638dp"
        android:ems="10"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextNumber2"
        android:hint="enter number"
        android:layout_width="238dp"
        android:layout_height="74dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="91dp"
        android:layout_marginLeft="91dp"
        android:layout_marginTop="133dp"
        android:layout_marginEnd="82dp"
        android:layout_marginRight="82dp"
        android:layout_marginBottom="524dp"
        android:ems="10"
        android:inputType="number" />

    <Button
        android:id="@+id/add1"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="83dp"
        android:layout_marginLeft="83dp"
        android:layout_marginTop="321dp"
        android:layout_marginEnd="88dp"
        android:layout_marginRight="88dp"
        android:layout_marginBottom="332dp"
        android:text="@string/add" />

    <Button
        android:id="@+id/subtract2"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="83dp"
        android:layout_marginLeft="83dp"
        android:layout_marginTop="415dp"
        android:layout_marginEnd="88dp"
        android:layout_marginRight="88dp"
        android:layout_marginBottom="238dp"
        android:text="subtract" />

    <Button
        android:id="@+id/multiply3"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="80dp"
        android:layout_marginLeft="80dp"
        android:layout_marginTop="609dp"
        android:layout_marginEnd="91dp"
        android:layout_marginRight="91dp"
        android:layout_marginBottom="44dp"
        android:text="multiply" />

    <Button
        android:id="@+id/divide4"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="82dp"
        android:layout_marginLeft="82dp"
        android:layout_marginTop="512dp"
        android:layout_marginEnd="89dp"
        android:layout_marginRight="89dp"
        android:layout_marginBottom="141dp"
        android:text="divide" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="202dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="94dp"
        android:layout_marginLeft="94dp"
        android:layout_marginTop="234dp"
        android:layout_marginEnd="115dp"
        android:layout_marginRight="115dp"
        android:layout_marginBottom="444dp"
        android:text="result"
        android:textSize="20sp" />

    <Button
        android:id="@+id/clear"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginEnd="13dp"
        android:layout_marginRight="13dp"
        android:layout_marginBottom="419dp"
        android:text="Clear" />
</RelativeLayout>
