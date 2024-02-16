# Cardio-X

Cardio-X is a device built to predict a heart attack before it occurs utilizing the 3-lead ECG system, a deep learning model and a mobile application. The detection of the heart signals is carried out through a wearable vest. The device Cardio-X can be described in three major parts: the sensory unit, comparison unit and mobile application.

* Sensory Unit
Heart signals are sensed by the III-Lead ECG sensor AD8232 placed inside a padded layer of the vest. Captured signals are then transferred to the ESP8266 module to process. Each ECG signal is represented by 140 data points and sent to the Firebase through Wi-Fi. The whole sensory unit is powered by a Li-ion battery. 

* Comparison Unit
Once the Firebase is updated with a set of new ECG signals as a stream of 140 data points, it is directly sent to the Deep Learning (DL) model which operates in the cloud server. The DL model used here is the Long Short-Term Memory (LSTM) autoencoder. A 5000 ECG signal dataset, each represented by 140 points, is used with the DL model including both normal and abnormal ECGs. After the comparison, the output result, whether the received signal is normal or not, will be sent through an Application Program Interface (API) to the mobile application.

* Mobile Application
The API connects the mobile app, the Firebase, and the DL model. Once the user clicks on ‘start’, the latest ECG signals uploaded to the Firebase will run through the DL model, process, and send the final output to the mobile application. The app will display the result as to whether the patient is at heart attack risk or not within 30-40 seconds.

![Flow Diagram](https://github.com/Mithara99/Cardio-X/assets/109811098/dfadbaf5-93fe-4d16-901d-c099b32b4eb9)

Watch the video!
![Cardio-X Video](https://drive.google.com/file/d/1m29li0GRjAQ2ru8W5z3auoMRo2MzwtGq/view?usp=sharing)



