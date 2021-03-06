# OpenFace + OSC Client

## WIKI
This is a forked version of "OpenFace: an open source facial behavior analysis toolkit" - https://github.com/TadasBaltrusaitis/OpenFace

**For instructions of how to install/compile/use the project please see [WIKI](https://github.com/TadasBaltrusaitis/OpenFace/wiki)**

More details about the project - http://www.cl.cam.ac.uk/research/rainbow/projects/openface/

**This Versoin is adding an OSC client so the project is easier to interface with OSC based projects.**

This Project allows easily create face controlled interfaces and interactive experiences. The data coming out from OpenFace is sent over the OSC protocol, making it easy to connect with many popular prototyping and interaction design platform such as Processing, TouchDsigner, Max/MSP, vvvv, Arduino, ect.

Using OSC also allows the data to be sent to a remote server, thus allowing using OpenFace to control remote applications and hardware.

## OSC Functionality

The OSC client is currently incorporated into the "FaceLandmarkVid.cpp" Project.

The face landmarks, gaze and pose data is sent to localhost "127.0.0.1" over port 6448.

#### The OSC Channels:

General face landmarks:
- "/openFace/faceLandmarks"

Eyes landmarks:
- "/openFace/rightEye"
- "/openFace/leftEye"

Gaze vectors:
- "/openFace/gazeVectorR"
- "/openFace/gazeVectorL"

Head Pose (Position and Anlge):
- "/openFace/headPose"

Face action units:
- "/openFace/ActionUnits"

**The Face Action Units extraction is a key feature in OpenFace which makes it a great tool for live emotion analysis.**

The "/openFace/ActionUnits" channel transmits 17 values, which represent Action Units:  1, 2, 4, 5, 6, 7, 9, 10, 12, 14, 15, 17, 20, 23, 25, 26, and 45. 
The values range is: 0 (not present), 1 (present at minimum intensity), 5 (present at maximum intensity).

You can find more information about AUs and how to use them to analyse emotion <a href="https://en.wikipedia.org/wiki/Facial_Action_Coding_System">here</a> and <a href="https://www.cs.cmu.edu/%7Eface/facs.htm">here</a>
More information about how OpenFace handles the Action Units can be found <a href="https://github.com/TadasBaltrusaitis/OpenFace/wiki/Action-Units">here </a>

You can use OSCdata monitor for an easy data peview (make sure to add port 6448): https://www.kasperkamperman.com/blog/osc-datamonitor/

You can find examples of using the data on different platforms in: "./osc_examples"

![Sample Gaze Tracking](https://github.com/yurikleb/OpenFace/blob/master/imgs/GazeTracking.gif)

If visual studio throws an import error, make sure the project settings match the screenshots in the "./osc_settings" folder

## Functionality

The system is capable of performing a number of facial analysis tasks:

- Facial Landmark Detection

![Sample facial landmark detection image](https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/multi_face_img.png)

- Facial Landmark and head pose tracking (links to YouTube videos)

<a href="https://www.youtube.com/watch?v=V7rV0uy7heQ" target="_blank"><img src="http://img.youtube.com/vi/V7rV0uy7heQ/0.jpg" alt="Multiple Face Tracking" width="240" height="180" border="10" /></a>
<a href="https://www.youtube.com/watch?v=vYOa8Pif5lY" target="_blank"><img src="http://img.youtube.com/vi/vYOa8Pif5lY/0.jpg" alt="Multiple Face Tracking" width="240" height="180" border="10" /></a>

- Facial Action Unit Recognition

<img src="https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/au_sample.png" height="280" width="600" >

- Gaze tracking (image of it in action)

<img src="https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/gaze_ex.png" height="182" width="600" >

- Facial Feature Extraction (aligned faces and HOG features)

![Sample aligned face and HOG image](https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/appearance.png)

#### Facial landmark detection and tracking

**Constrained Local Neural Fields for robust facial landmark detection in the wild**
Tadas Baltrušaitis, Peter Robinson, and Louis-Philippe Morency. 
in IEEE Int. *Conference on Computer Vision Workshops, 300 Faces in-the-Wild Challenge*, 2013.  

#### Eye gaze tracking

**Rendering of Eyes for Eye-Shape Registration and Gaze Estimation**
Erroll Wood, Tadas Baltrušaitis, Xucong Zhang, Yusuke Sugano, Peter Robinson, and Andreas Bulling 
in *IEEE International. Conference on Computer Vision (ICCV)*,  2015 

#### Facial Action Unit detection

**Cross-dataset learning and person-specific normalisation for automatic Action Unit detection**
Tadas Baltrušaitis, Marwa Mahmoud, and Peter Robinson 
in *Facial Expression Recognition and Analysis Challenge*, 
*IEEE International Conference on Automatic Face and Gesture Recognition*, 2015 

# Copyright

Copyright can be found in the Copyright.txt

You have to respect boost, TBB, dlib, and OpenCV licenses.

# Commercial license

For inquiries about the commercial licensing of the OpenFace toolkit please contact innovation@cmu.edu

# Final remarks

I did my best to make sure that the code runs out of the box but there are always issues and I would be grateful for your understanding that this is research code and not full fledged product. However, if you encounter any problems/bugs/issues please contact me on github or by emailing me at Tadas.Baltrusaitis@cl.cam.ac.uk for any bug reports/questions/suggestions. 

