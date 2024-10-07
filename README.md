# Driver-Drowsiness-Detection-System  
In recent years driver fatigue is one of the major causes of vehicle accidents in the world. A direct way of measuring driver fatigue is measuring the state of the driver i.e., drowsiness. 
Hence, it is very important to detect the drowsiness of the driver to save life and property. This project is aimed towards developing a prototype of drowsiness detection system. 
This system is a real time system which captures image continuously and measures the state of the eye and mouth according to the specified algorithm and gives warning if required. 
Driver drowsiness detection systems help prevent accidents by alerting the driver whenever the system finds signs of drowsiness through the use of eye and yawn detection.  
  
### Proposed Approach:  
• First of all, we have captured video from the camera and detected face from the video frames.  
• From the extracted frames, we will derive the eyes from the face. This will be used in calculating the time for which eyes are closed.  
• After that we have calculated Eyes Aspect Ratio (EAR) and compared that to threshold ratio. If the EAR is less than the threshold then an alert message will be displayed upon the screen.  
• Along with Eye detection, the program will also detect mouth and keep a counter for number of yawns in a fixed interval of time. Yawn will be detected in a similar manner to blink detection.  
• We have calculated Mouth Aspect Ratio (MAR) and compared that to threshold ratio. If the MAR is greater than the threshold, then it will be counted as a yawn and the yawn counter will increase. 
If the yawn counter crosses the threshold value, then an alert message will be displayed upon the screen.  
• Also, apart from the message upon the screen, we will be sending a message on the phone of the emergency contact of driver along with the location of the driver.  

### Requirements  
To run the detection system install anaconda prompt. Navigate to the folder where the repository is saved and execute the following commands on anaconda.  
  
conda create --name opencv-env python=3.8  
activate opencv-env  
pip install numpy scipy matplotlib scikit-learn jupyter imutils playsound os geocoder twilio  
pip install opencv-contrib-python  
conda install -c conda-forge dlib  
  
Now the file should execute smoothly with the command:  
python detect_drowsiness.py --webcam 0 --alarm alarm.wav  

### Note  
Create an account on twilio and get account ID and authorized token. Replace them in the python file accordingly.  
Also replace the from number in lines 133 and 162 with the number provided by twilio.  
In lines 134 and 163, replace the number with the number of the emergency contact.  
