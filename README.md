# RASPBERRYPI-HAND_TRACKING_OPENCV

## DESCRIPTION:

i am using mediapipe and opencv to make a handtracking python code

## Libraries/Module's used:
pip install opencv-python

pip install opencv-contrib-python

pip install mediapipe

pip install --upgrade "protobuf<=3.20.1"

## CODE:

``````
import cv2
import mediapipe as mp
import time

cap=cv2.VideoCapture(0)

mphands=mp.solutions.hands
hands=mphands.Hands()
mpDraw=mp.solutions.drawing_utils
while True:

    success,img=cap.read()
    imgRGB=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
    results=hands.process(imgRGB)
    #print(results.multi_hand_landmarks)
    if results.multi_hand_landmarks:
        for handLms in results.multi_hand_landmarks:
            mpDraw.draw_landmarks(img,handLms,mphands.HAND_CONNECTIONS)
    cv2.imshow("IMAGE",img)
    cv2.waitKey(1)
``````
## TESTING CODE: (this code can detect upto 2 hands)

![IMG20220831164018](https://user-images.githubusercontent.com/102857010/187665721-6822364b-0575-4325-9e21-70548abbd3e3.jpg)

![IMG20220831163959](https://user-images.githubusercontent.com/102857010/187666152-06592a71-98cf-488e-a9a1-0d143f0921e3.jpg)



