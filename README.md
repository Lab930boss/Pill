# Pill
This project is not intented for public use so all the environemnt setting and installation procedure will not work in other computer

## Requirement 
* The following components are already installed in Mindspree deep learning server
- Darknet Yolo
- Linux PC with Nvida GPU
- OpenCV for Linux (Optional)

## How to train
  In order to train darkent for this application, you need to following the steps below.
  * Prepare for the training and testing data
  
  - Training image file path  
    Place all the images and annotation file in this folder
    ~/Github/darknet/data/img   br />
    
    
![Alt text](https://github.com/Lab930boss/DnnSetup/blob/master/nvidia%20driver%20info.png?raw=true "GPU info") <br />
  
  
  - Set up the configuration file
    In this file, training and validation file path is defined. 
    ~/Github/darknet/data/obj.data 
    
    
    
    Contents
      - classes =1
      - train = data/train.txt   
      - valid = data/train.txt   --> In this case train data is used for validation
      - names = data/obj.names
      - backup backup
