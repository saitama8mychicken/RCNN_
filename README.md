# RCNN_

This works on selective search algorithm

    This generates the initial subsegmentation of image
    
    select mini candidate region
    
    use greedy search algorithm to recursively combine similar looking regions into lareger once
    
    use generative region to find the final regions
    
Steps in RCNN

1 - Input Images

2 - region Proposals - Selective Search

3 - Wrapped the regions

4 - Pretrained Cnn Model ( Alexnet, VGG16)

5 - SVM to classify the model


## Selective Search :

    It uses an algorithm of **(region based proposal algorithm)** mainly for object detection
    
        Region proposals can be noisy, overlapping and may not contain the object perfectly
        
        Amongst these region proposals, there will be a proposal which will be very close to the 
        
        actual object in the image
        
        The region proposal with high probablity scores are locations of the object
        
    Designed for fast object detectionpwith high recall 
    
    Based on computing hierarchical grouping of similar regions based on color, texture, size, and shape compatibility
    
    
## Wrapped Images:

  Extract region proposals for all images
  
  For each region: warp to cnn input size, run foreward through CNN, save pool5 features to disk
  
  
  
## Pretrained Model (Transfer learning) :

    **" Model which is trained by someone to solve the similar problems "**
    
    
Instead of making a model from scratch using the build model to solve similar problems


Suppose you want to make a self driving car, so instead of training your model from scratch you can directly use the pretrained
(inception model from google) model to save  your time and computational cost as well. This is known as transfer learning.

### Types of transfer learning:

1 - TYPE I   ->  Train the entire model (large dataset but different from trained model's dataset)

2 - TYPE II  ->  Train some layer and leave other frozen (large dataset similer to the trained dataset) 

3 - TYPE III ->  Keep the full model greeze and feed the dense layer according to classifier ( small dataset and simier to pretrained model's dataste)


## SVM to classify the class:

"Support vector machine is a supervised machine learning algorithm which can be used for classification and regression"

Improve classification accuracy by linear SVM classifier on the top of the features extraxtxed layer by the convolutional base

Helps to redure dumentions of pretrained model

Binary SVM is used for each classes present in classification



