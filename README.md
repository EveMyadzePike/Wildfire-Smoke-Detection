[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JasonManesis/Convolutional-Neural-Network-Classifier-MNIST/blob/main/CNN_MNIST_PyTorch_VISUALS.ipynb)

# Wildfire Smoke Detection.
Convolutional neural network model based on the architecture of the **Faster-RCNN** for wildfire smoke detection. For this project we used a pretrained model on ImageNet dataset, from detectron2's "model zoo", and fine-tune it for the task of wildfire smoke detection from optical image data.

## Dataset Properties.
<div align="left">
 
This dataset is released by **AI for Mankind** in collaboration with **HPWREN** (High Performance Wireless Research and Education Network), and is licensed under the [**Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License**](https://creativecommons.org/licenses/by-nc-sa/4.0/). 
 
 **AI For Mankind** is a 501(c)(3) nonprofit organization with the mission of mobilizing the tech community to work on world challenging problems using AI and Data. We organize tech talks, workshops, and hackathons. We want to build a grassroot community of volunteers creating solutions using AI and Data to bring positive impacts to society at large.       (https://aiformankind.org/) 
 
The **High Performance Wireless Research and Education Network (HPWREN)**, a University of California San Diego partnership project led by the San Diego Supercomputer Center and the Scripps Institution of Oceanography's Institute of Geophysics and Planetary Physics, supports Internet-data applications in the research, education, and public safety realms. (http://hpwren.ucsd.edu/)
 
 
The above dataset is available in **2** different versions in **Pascal VOC** annotation format:
 
 :arrow_right_hook:   Bounding Box Annotated Wildfire Smoke Dataset Version 1.0 with **744** annotated images. 
 
 :link:[ **BBAWS Dataset v1.0 - Pascal VOC**](https://drive.google.com/file/d/1sEB77bfp2yMkgsSW9703vwDHol_cK6D5/view?usp=sharing)
 
 :arrow_right_hook:  Bounding Box Annotated Wildfire Smoke Dataset Version 2.0 with **2192** annotated images. 
 
:link:[ **BBAWS Dataset v2.0 - Pascal VOC**](https://drive.google.com/drive/folders/1IKXN2-hxTrEQsIIKOxiUAuLgoxubA9Wq?usp=sharing)

The **first version** of the dataset is also available in **COCO** annotation format by **Roboflow**:
 
:arrow_right_hook: Bounding Box Annotated Wildfire Smoke Dataset Version 1.0 with **744** annotated images. 
 
 :link: [ **BBAWS Dataset v1.0 - COCO**]( https://public.roboflow.com/object-detection/wildfire-smoke)
 


_For this project we used the dataset in **COCO** annotation format provided by Roboflow._

</div align="left">

## Model Architecture
The model architecture is based on the general archtecture of the **Faster-RCNN**, which includes the main modules of **Feature Pyramid Network** and **Region Proposal Network** as well as the model of **Fast-RCNN**.

<img src="https://miro.medium.com/max/2000/1*Wvn0WG4XZ0w9Ed2fFYPrXw.jpeg">

_Image source: https://miro.medium.com/max/2000/1*Wvn0WG4XZ0w9Ed2fFYPrXw.jpeg_

### **Feature Pyramid Network (FPN)**

<div align="center">
 
### Bottom-up pathway -> ResNet50 :
<img src="https://www.researchgate.net/publication/349646156/figure/fig4/AS:995806349897731@1614430143429/The-architecture-of-ResNet-50-vd-a-Stem-block-b-Stage1-Block1-c-Stage1-Block2.png">
 
_**Image source: https://www.researchgate.net/publication/349646156/figure/fig4/AS:995806349897731@1614430143429/The-architecture-of-ResNet-50-vd-a-Stem-block-b-Stage1-Block1-c-Stage1-Block2.png**_ 

### Top-down pathway
</div align="center">


### **Region Proposal Network (RPN)**

<img src="https://davidstutz.de/wordpress/wp-content/uploads/2018/02/ren.jpg">
 
_**Image source: https://davidstutz.de/wordpress/wp-content/uploads/2018/02/ren.jpg**_ 





### **Fast-RCNN**


## Model Performance
 
 Performance Metrics:

|          Metric        |         IoU     |      Area   |      maxDets |   Score  |
|:----------------------:|:---------------:|:-----------:|:------------:|:--------:|
|Average Precision  (AP) |0.50:0.95        |    all      | 100          | **0.547**|
|Average Precision  (AP) |0.50             |    all      |100           | **0.909**|
|Average Precision  (AP) |0.75             |    all      | 100          | **0.561**|
|Average Precision  (AP) |0.50:0.95        |  small      | 100          | **0.318**|
|Average Precision  (AP) |0.50:0.95        | medium      | 100          | **0.497**|
|Average Precision  (AP) |0.50:0.95        | large       |         100  | **0.646**|
|Average Recall     (AR) |0.50:0.95        | all         | 1            | **0.615**|
|Average Recall     (AR) |0.50:0.95        | all         |10            | **0.620**|
|Average Recall     (AR) |0.50:0.95        | all         | 100          | **0.620**|
|Average Recall     (AR) |0.50:0.95        | small       | 100          | **0.443**|
|Average Recall     (AR) |0.50:0.95        | medium      | 100          | **0.584**|
|Average Recall     (AR) |0.50:0.95        | large       | 100          | **0.707**|


## Results
### Images:


Solarized dark                                                    |     Solarized Ocean
:----------------------------------------------------------------:|:-------------------------:
<img width="500" height="400" src="/Images/Results_image_1.png">  |  <img width="500" height="400" src="/Images/Results_image_2.png">



### Videos:


https://user-images.githubusercontent.com/74200033/130096189-c42585e5-79ea-4cef-aa5f-cace7345a81b.mp4



## Requirements

    torch == 1.9.0+cu102                               numpy == 1.19.5                             json == 2.0.9
    torchvision == 0.10.0+cu102                        yaml == 5.1                                 fiftyone == 0.12.0
    pyyaml == 5.1                                      pandas == 1.3.2                             IPython == 5.5.0
    detectron2 == 0.5                                  cv2 == 4.1.2
                  
  
