# Pill
This project is not intented for public use so all the environemnt setting and installation procedure will not work in other computer

## Requirement 
* The following components are already installed in Mindspree deep learning server
- Darknet Yolo
- Linux PC with Nvida GPU
- OpenCV for Linux (Optional)

## How to train
  In order to train darkent for this application, you need to follow the steps below. <br />
  Please go to the reference site and read it through. This is very important <br />
  ( Reference site:  https://timebutt.github.io/static/how-to-train-yolov2-to-detect-custom-objects/ ) <br />
  * Prepare for the training and testing data
  
  - Training image file path  
    Place all the images and annotation file in this folder. Each image file is paried with annotation file.
    Please check the image below 
    ~/Github/darknet/data/img   <br />
    
    The annotation field structure is as follows
    - [category number] [object center in X] [object center in Y] [object width in X] [object width in Y] <br />
    In our case, we only detect pill so there is only one category. The category will be alwyas 0 <br />
    
    - For easier annotation, you need to use the following tool <br />
      https://github.com/Lab930boss/Yolo_mark <br />
      
![Alt text](https://github.com/Lab930boss/Pill/blob/master/IMG_0004.JPG?raw=true "training image and annotation") <br />
  
  

  * Set up obj.data file <br />
    In this file, training and validation file paths are defined.  <br />
    ~/Github/darknet/data/obj.data 
    
    Contents
      - classes =1
      - train = data/train.txt   
      - valid = data/train.txt   --> In this case train data is used for validation
      - names = data/obj.names
      - backup backup

  * Set up cfg/yolo-obj.cfg that defines DNN structure

  * Training command 
    ~/Github/darknet/darknet detector train data/obj.data cfg/yolo-obj.cfg darknet19_448.conv.23
    - If darknet doesn't work, use darknet_train instead
    - The darknet19_448.conv.23 is the pretrained network
    
    Note: When you edit cfg file please be careful about the folliwing rule
    set classes=1, the number of categories we want to detect
    set filters=(classes + 5)*5 in our case filters=30
    
  * Test command 
        ~/Github/darknet/darknet detector test data/obj.data cfg/yolo-obj.cfg yolo-obj1000.weights data/testimage.jpg  <br />
        - If darknet doesn't work, use darknet_train        

  ** Note
   Due to compiing issue, please use ~/Github/darknet2018/darknet  instead of ~/Github/darknet
        
    
    
    
