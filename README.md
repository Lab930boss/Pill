# Pill
This project is not intented for public use so all the environemnt setting and installation procedure will not work in other computer

## Requirement 
* The following components are already installed in Mindspree deep learning server
- Darknet Yolo
- Linux PC with Nvida GPU
- OpenCV for Linux (Optional)

## How to train
  In order to train darkent for this application, you need to following the steps below.
  Reference site:  https://timebutt.github.io/static/how-to-train-yolov2-to-detect-custom-objects/
  * Prepare for the training and testing data
  
  - Training image file path  
    Place all the images and annotation file in this folde. Each image file is paried with annotation file.
    Please check the image below 
    ~/Github/darknet/data/img   <br />
    
    The annotation field structure is as follows
    - [category number] [object center in X] [object center in Y] [object width in X] [object width in Y] <br />
    In our case, we only detect pill so there is only one category. The category will be alwyas 0 <br />
    
![Alt text](https://github.com/Lab930boss/Pill/blob/master/IMG_0004.JPG?raw=true "training image and annotation") <br />
  
    - For easier annotation, you need to use the folliwing tool <br />
      https://github.com/Lab930boss/Yolo_mark <br />


  * Set up the configuration file
    In this file, training and validation file path is defined. 
    ~/Github/darknet/data/obj.data 
    
    Contents
      - classes =1
      - train = data/train.txt   
      - valid = data/train.txt   --> In this case train data is used for validation
      - names = data/obj.names
      - backup backup

  * 
