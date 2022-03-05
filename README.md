# Brain-Tumor-Detection
https://abhishekjha2468.medium.com/brain-tumor-detection-6b5ac01a00a0

## Introduction :
Abnormalities in the brain are now being identified with the help of BRAIN MRI SCAN, Magnetic resonance imaging (MRI) of the brain is a safe and painless test that uses a magnetic field and radio waves to produce detailed images of the brain and the brain stem. Identification of abnormalities in the brain needs a Specialist Doctor Consultant.
Also, identification of such abnormalities is very important, else this could lead us to major diseases like cancer.
From a business point of view, The machine learning model which identifies abnormalities in the brain given their MRI scan can counter a large number of patients, also it is cost-effective

## Problem Statement :
Using the concept of Machine learning and Deep Learning we have to perform a computer vision task, where we have to do segmentation on a given Brain MRI SCAN in order to identify Abnormalities on the brain Accordingly.

## APPROACH
I was given 110 patient data files in separate folders in this case study, which include their brain mri scan and their respective mask image for finding abnormalities in the mri scan. To clean up my data, I create two folders, one for scan images and the other for mask images.

Then i did some image analysis to gain some insights from the data i was utilising, and as a result, i came up with some interesting ideas such as the location of abnormality in the scan, the dominant hue of abnormality in the scan, the percentage of pixel classified as abnormality, and so on.

Then I created a dataframe containing scan image path, mask image path, and a label that tells us whether the scan image is abnormal or not. The purpose of introducing this column is that, because my dataset is imbalanced between abnormal and normal images,my train and test distributions may change if I randomly split the data. To counteract this, I introduced a label column so that I can stratify split my dataset. Then, on an imagenet dataset, I load a pre-trained U-Net architecture and freeze its encoder weights. Then I import my dataset from the image generator (flow from DataFrame), do prior image scaling, and augment the training image.

Then, for 50 epochs, i train our Unet architecture, resulting in a train IOU score of 0.42 and a test IOU score of 0.4.

## PIPELINE
![image](https://user-images.githubusercontent.com/66833049/156868496-d2c99915-088c-45f8-bde1-7deaae55f8f5.png)
![image](https://user-images.githubusercontent.com/66833049/156870251-183fe117-ed3a-4880-b332-41df1c66951c.png)

## RESULT
![image](https://user-images.githubusercontent.com/66833049/156870262-bf912129-6158-4187-aea6-a5d90c19c54b.png)

## Conclusion
After examining the model's predictions, I discovered that the best forecasts were made for scans in which the abnormality is separated in region by a considerable bold hue and can also be easily classified by our nacked eye. Despite the fact that our model performs admirably in almost all of the scan, with extremely high precision.

