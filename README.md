# Sign Language Prediction
Sign language prediction using CNN
There is a need of a method or an application that can recognize sign language gestures so that the communication is possible even if someone does not understand sign language. With this work, we intend to take a basic step in bridging this communication gap using Sign Language Recognition.

# A quick sneak-peak into what was done
1.Firstly, we've created 44 gesture samples using OpenCV, in which,for each gesture we've captured 1200 images each of 50x50 pixels.All theses images were in grayscale which is stored in the gestures/ folder. The pictures were flipped using flip_images.py. This script flips every image along the vertical axis. Hence each gesture has 2400 images.
2. Created a CNN using keras and TensorFlow. All the gestures that are present in this repo are basic, if you want to add more gestures, you can create your own gestures.
3. Then used the model which was trained using Keras on a video stream.

# Requirements
Python 3.x

Tensorflow 1.5

Keras

OpenCV 3.4

h5py

pyttsx3

Now,let's dive deep into steps done. 

# Creating a gesture
Firstly, set your hand histogram. You do not need to do it again if you've already done it. But you do need to do it if the lighting conditions change. To do so type the command given below and follow the instructions below.

```
python set_hand_hist.py
```
A windows "Set hand histogram" will appear.
"Set hand histogram" will have 50 squares (5x10).
Put your hand in those squares. Make sure your hand covers all the squares.
Press 'c'. Another window will appear named "Thresh".
On pressing 'c' only white patches corresponding to the parts of the image which has your skin color should appear on the "Thresh" window.
Make sure all the squares are covered by your hand.
In case if that didn't work, then move your hand a little bit and press 'c' again. Repeat this until you get a good histogram.
After you get a good histogram press 's' to save the histogram. All the windows close.

We already have 44 gestures. If you want to add gestures, use the instruction below:
```
python create_gestures.py
```
On executing the above intruction, you will have to enter your gesture number and give it a name. Then a window name "Capturing gestures", in which you will find a green box, in which you will have to capture your gestures. And a counter will make a count on number of gestures stored. Press 'c' when you are ready with your gesture. Capturing gesture will begin after a few seconds. Move your hand a little bit here and there. You can pause capturing by pressing 'c' and resume it by pressing 'c'. Capturing resumes after a few secondAfter the counter reaches 1200 the window will close automatically. 

Now, after capturing the gestures, you need to flip the images using instruction below:
```
python flip_images.py
```

Now, you need to load the images using the instruction below:
```
python load_images.py
```

# Displaying the gestures
To see all the gestures that are stored in 'gestures/' folder run this command
```
python display_all_gestures.py
```

# Training a model
training can be done with either Tensorflow or Keras. If you want to train using Tensorflow then run the cnn_tf.py file. If you want to train using Keras then use the cnn_keras.py file.
```
python cnn_tf.py
python cnn_keras.py
```
# Getting the model reports
To get the classification reports about the model make sure you have test_images and test_labels file which are generated by load_images.py. In case you do not have them run load_images.py file again. Then run this file
```
python get_model_reports.py
```
# Testing the gestures
Firstly, set your hand hiatograph using the below instruction
```
python set_hand_hist.py
```
Now, to recognize the gesture, use the below instruction
```
python recognize_gesture.py
```
You will have a small green box inside which you need to do your gestures.

Finally after all the training, now use the below instruction for sign language prediction
```
python fun_util.py
```

# Citation
Saha, D.. (2018, May 9). Sign-Language (Version 1). figshare. https://doi.org/10.6084/m9.figshare.6241901.v1A a simple CNN project.

