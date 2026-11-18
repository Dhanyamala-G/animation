# Ex.No: 6 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:



## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Dhanyamala Gokul Kumar
Registeration Number : 212225040066
*/
```
### MainActivity.java
```
 package com.example.animation;

import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

 public class MainActivity extends AppCompatActivity {

     // Declare variables for ImageView and Buttons
     private ImageView imageView;
     private Button blink, rotate, fade, move, slide, zoom, stop;

     @Override
     protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);

         // Initialize ImageView and Buttons using their IDs
         imageView = findViewById(R.id.imageView);
         blink = findViewById(R.id.blink);
         rotate = findViewById(R.id.rotate);
         fade = findViewById(R.id.fade);
         move = findViewById(R.id.move);
         slide = findViewById(R.id.slide);
         zoom = findViewById(R.id.zoom);
         stop = findViewById(R.id.stop);

         // Set up click listeners for each button to start corresponding animations
         createAnimation(blink, R.anim.blink);
         createAnimation(rotate, R.anim.rotate);
         createAnimation(fade, R.anim.fade);
         createAnimation(move, R.anim.move);
         createAnimation(slide, R.anim.slide);
         createAnimation(zoom, R.anim.zoom);

         // Set up click listener for stop button to clear any ongoing animation
         stop.setOnClickListener(v -> imageView.clearAnimation());
     }

     // Function to set up an animation for a given view and animation resource ID
     private void createAnimation(View view, int animResId) {
         view.setOnClickListener(v -> {
             // Load the animation from the specified resource ID
             Animation animation = AnimationUtils.loadAnimation(MainActivity.this, animResId);
             // Start the animation on the ImageView
             imageView.startAnimation(animation);
         });
     }
 }
```
### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="121dp"
        android:layout_height="118dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.221"
        app:srcCompat="@android:drawable/star_big_on" />

    <Button
        android:id="@+id/move"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="@string/move"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.613" />

    <Button
        android:id="@+id/blink"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="Blink"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/move"
        app:layout_constraintHorizontal_bias="0.449"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.616" />

    <Button
        android:id="@+id/fade"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="@string/fade"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.475"
        app:layout_constraintStart_toEndOf="@+id/move"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.613" />

    <Button
        android:id="@+id/rotate"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_marginTop="59dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="@string/clockwise"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.083"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/blink"
        app:layout_constraintVertical_bias="0.165" />

    <!--To start the zoom animation of the image-->

    <Button
        android:id="@+id/slide"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="@string/slide"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.882"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/fade"
        app:layout_constraintVertical_bias="0.165" />

    <Button
        android:id="@+id/zoom"
        style="@style/TextAppearance.MaterialComponents.Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_marginTop="92dp"
        android:layout_weight="1"
        android:padding="3dp"
        android:text="@string/zoom"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/move"
        app:layout_constraintVertical_bias="0.174" />

    <Button
        android:id="@+id/stop"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/stop_animation"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/zoom" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
### blink.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500"
        android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
```
### fade.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/accelerate_interpolator">

    <!-- duration is the time for which animation will work-->
    <alpha
        android:duration="1000"
        android:fromAlpha="0"
        android:toAlpha="1" />

    <alpha
        android:duration="1000"
        android:fromAlpha="1"
        android:startOffset="2000"
        android:toAlpha="0" />

</set>
```
### move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/linear_interpolator"
    android:fillAfter="true">

    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>
```
### rotate.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set
    xmlns:android="http://schemas.android.com/apk/res/android">
    <rotate
        android:duration="6000"
        android:fromDegrees="0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:toDegrees="360" />

    <rotate
        android:duration="6000"
        android:fromDegrees="360"
        android:pivotX="50%"
        android:pivotY="50%"
        android:startOffset="5000"
        android:toDegrees="0" />

</set>
```
### slide.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >
    <scale
        android:duration="500"
        android:fromXScale="1.0"
        android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>
```
### zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >

    <scale
        android:interpolator="@android:anim/linear_interpolator"
        android:duration = "1000"
        android:fromXScale = "1"
        android:fromYScale = "1"
        android:pivotX = "50%"
        android:pivotY = "50%"
        android:toXScale = "2"
        android:toYScale = "2"/>
</set>
```

## OUTPUT

<img width="1492" height="742" alt="image" src="https://github.com/user-attachments/assets/17cdb468-ff4e-4869-8343-b691dfbe6ac8" /><br>

<img width="1487" height="741" alt="image" src="https://github.com/user-attachments/assets/ad6e8f1c-3195-48b1-854f-ee57d532192a" /><br>

<img width="1492" height="742" alt="image" src="https://github.com/user-attachments/assets/f0890f7d-395e-4fe0-bfb4-4a2bf1ba1ec8" /><br>

<img width="1493" height="741" alt="image" src="https://github.com/user-attachments/assets/35708e95-17b4-4c12-b5ed-e3bb91d35f52" /><br>

<img width="1493" height="742" alt="image" src="https://github.com/user-attachments/assets/fde41c14-eb24-4f8e-80b1-1e85bff30320" /><br>

<img width="1493" height="742" alt="image" src="https://github.com/user-attachments/assets/d1d3be4f-12a7-42bc-8722-0821aa88f21a" /><br>

<img width="1492" height="742" alt="image" src="https://github.com/user-attachments/assets/fb4f599d-1d7a-4dfc-94de-fd13fe2f90b9" /><br>







## RESULT
A application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio is successfully created.
