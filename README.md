# ImageChangeApp-Android-

XML FILE:-
(activity_main.xml)
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/activity_main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.example.imagechangeapp.MainActivity">

    <ImageView
        android:id="@+id/img1"
        android:layout_width="351dp"
        android:layout_height="wrap_content"
        android:layout_above="@+id/button"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_marginStart="30dp"
        android:layout_marginTop="71dp"
        android:layout_marginEnd="30dp"
        android:layout_marginBottom="29dp"
        android:contentDescription="TODO" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="126dp"
        android:layout_marginEnd="134dp"
        android:layout_marginBottom="214dp"
        android:text="@string/change_image" />
</RelativeLayout>


JAVA FILE:-
(MainActivity.java)

package com.example.imagechangeapp;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {

    Button b1;
    ImageView iv;
    boolean flag;
    private final int[] images;

    {
        images = new int[]{R.drawable.ganeshjii, R.drawable.durgamata, R.drawable.hanumanjii, R.drawable.krishnajii, R.drawable.shivjii};
    }

    int i=0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        iv=(ImageView) findViewById(R.id.img1);
        b1=(Button) findViewById(R.id.button);

        flag=true;

        b1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                iv.setImageResource(images[i]);
                i++;
                if(i==5)
                    i=0;
            }
        });
    }
}
