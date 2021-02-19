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
