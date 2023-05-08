# 6D-Pose-Estimation


Pose Estimation is a computer vision technique that involves estimating the 3D position and orientation (i.e., rotation and translation) of an object in space, given one or more 2D images of the object. It is a fundamental task in robotics, augmented reality, manufacturing, and many other applications.

This repository contains code and resources for detailed Pytorch implementation of pose estimation algorithm, PoseCNN, that can be used to estimate the pose of objects in different scenarios. 


Pose CNN is a convolutional neural network (CNN) architecture that is specifically designed for the task of 6D pose estimation. It is a unique algorithm that uses a deep learning approach to estimate the position and orientation of an object in 3D space, given a 2D image of the object.

Pose CNN is unique because it is a learning-based method that combines both template-based and feature-based approaches to achieve high accuracy in pose estimation. It uses a 3D model of the object as a template and extracts features from the 2D image using a CNN. These features are then matched to the 3D template to estimate the object's pose.

Pose CNN also includes a refinement step that further improves the accuracy of the estimated pose. It uses a technique called iterative pose refinement, which iteratively refines the estimated pose by minimizing the difference between the projected 3D model and the 2D image.



## Results:



#### 1. Final estimates(Montage of Sample 5 images) (Got approx 41% accuracy, you can change the hyperpraramters and train more to get higher accuracy

<img width="720" alt="image" src="https://user-images.githubusercontent.com/86003669/227661528-57922f64-abbc-4839-9063-a790a285a8c8.png">






#### 2. Overall Loss(rotation, translation and segmentation):

![image](https://user-images.githubusercontent.com/86003669/227659193-684be76e-e442-4b92-8de8-c917527bfd54.png)



#### 3. Instance segmentation estimates:

![image](https://user-images.githubusercontent.com/86003669/227659280-27f8d685-2eb0-432a-831f-091c59fb7961.png)   



#### 4. Instance segmentation loss:

![image](https://user-images.githubusercontent.com/86003669/227659300-f5f8c1c0-f8c8-465c-8768-f0dafa17ec7f.png)






## Architecture:

![image](https://user-images.githubusercontent.com/86003669/227664294-1faeb746-d2a5-493d-98e9-750a88853791.png) 


## File Index:

#### p4_helper.py: Contains
* loss_cross_entropy(scores, labels)
* loss_Rotation(pred_R, gt_R, label, model)
* IOUselection(pred_bbxes, gt_bbxes, threshold)
* HoughVoting(label, centermap, num_classes=10)


#### pose_cnn.py: Contains
* PoseCNN(nn.Module)
* RotationBranch(nn.Module)
* TranslationBranch(nn.Module)
* SegmentationBranch(nn.Module)
* FeatureExtraction(nn.Module)
* eval(model, dataloader, device, alpha = 0.35)

#### pose_estimation.ipynb: Contains driver code and explanation for everything, involving data download links
#### rob599: Contains code checking functions
