import cv2from matplotlib
import pyplot as plt
import numpy as np
import imutils
import easyocr
cap=cv2.VideoCapture(0) #capturing the video
while True:
    ret,img=cap.read() #reading the frame
    reader=easyocr.Reader(['en']) #initializing the reader
    rezised=cv2.resize(img,(78,38)) #resizing the image
    result=reader.readtext(img) #reading the text from the image
    cv2.imshow('frame',img) 
    if cv2.waitKey(1) & 0xFF==ord('q'): #breaking the loop
        break
    print(result) #printing the result
