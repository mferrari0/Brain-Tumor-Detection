# Brain-Tumor-Detection

The notebook contains the steps required to build and train CNN learning model for the detection of brain tumors in magnetic resonance imaging (MRI) scans. The model is built using the Keras library with a TensorFlow backend and trained on a dataset of labeled brain MRI images.

### Technologies and Methods  
- CNN
- Python
- Keras
- Tensorflow
- matplotlib
- ResNet50

### Data Source

The dataset was provided by Jun Cheng and is available here: https://figshare.com/articles/dataset/brain_tumor_dataset/1512427
This brain tumor dataset containing 3064 T1-weighted contrast-inhanced images from 233 patients with three kinds of brain tumor: meningioma (708 slices), 
glioma (1426 slices), and pituitary tumor (930 slices). Additional information can be found here: https://figshare.com/articles/dataset/brain_tumor_dataset/1512427?file=7953679

<img src="https://raw.githubusercontent.com/mferrari0/Brain-Tumor-Detection/main/dataset.PNG" width="900" height="600">




### Approach
At first I tested the performance of a baseline model (95% f1 score). 
To increase its performance I tried:
- Data Augmentation
- Dropout
- Regularization
- Class weights
- Dynamic Learning rate
- Early stopping
Then I used the resnet50 model with transfer learning with different number of trainable layers. 

## SUMMARY

- Baseline CNN with 3 convolution layers show pretty good results for a quick deployment (95%).

- Data augmentation doesn't work well with MRI images, much lower results than without.

- Transfer learning: RESNet50 doesn't show a quick improvement over the baseline model, but can reach a f1 score over 97% with dynamic learning rate and early stopping.

- No false negatives for glioma or pituitary tumors. Only 3 meningioma MRI images are classified as not tumoral.

- Meningioma is the most difficult to optimize for --> it is also the most difficult to diagnose for oncologist

<img src="https://raw.githubusercontent.com/mferrari0/Brain-Tumor-Detection/main/training%20and%20validation%20acc.PNG" width="600" height="300">


![alt text](https://raw.githubusercontent.com/mferrari0/Brain-Tumor-Detection/main/scores.PNG)


### Further steps: 
  - try other models like VGG and Efficient Net
  - include visualizations for AI explainability (GradCAM)
