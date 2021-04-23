Description:

This project implements a 2-Class Object Detector model using Yolo v3 as well as the more recent Yolo v4 to detect Mask or No-mask. 
The classes are:
Class 0 - Face with Mask
Class 1 - Face without Mask
Given an input image or video with faces with and without masks, the model will ouput Mask or No Mask on all faces detected.

Detailed documentation on the steps and code are in the notebook files. Following are the steps at a high level:

1. Download and compile Darknet source - git clone https://github.com/AlexeyAB/darknet.git
2. Dataset contains images of people with mask and without mask, and the annotations are given in the txt files. 
3. Configure all the neccessary config files (class.names, .cfg, .data etc) and Hyperparameters values:
4. Download pre-trained weights(from ImageNet) to start with default weights for training
4. Perform YOLO Training
./darknet detector train yolov3-masks-setup.data yolov3-masks-train3.cfg backup/yolov3-masks-train2_best.weights -dont_show -map 2> train3_log.txt

5. Perform Inference using the trained weights

on image:
./darknet detector test yolov3-masks-setup.data yolov3-masks-test3.cfg backup/yolov3-masks-train3_best.weights test-image1.jpg -thresh .6 2> /dev/null

on video:
!./darknet detector demo yolov3-masks-setup.data yolov3-masks-test3.cfg backup/yolov3-masks-train3_best.weights test-video1.mp4 -thresh .6 -out_filename out-vid-yolyov3.avi -dont_show




