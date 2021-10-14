# unsupervised_anomaly_detection

## Dataset Type

Based on the used dataset in the training dataset
- Contaminated dataset: it contains both normal and anamolous elements in the training. 
- Uncontaminated dataset: The training data contains only normal samples. The methods that take this assumption are also refered weakly supervised approaches.

## UFDGAN 
#### Assumptions: 
- Contaminated training set 
- the anomaly percentage is known

#### Why based on the unsupervised contrastive learning will not work?

The dataset is composed of multi modal data, but only one mode is labaled as anomaly. If the dataset is to a human, he will not be able to the anomaly exactly.
For that, the 

<p align="center">
<img src="assets/training_samples.JPG" alt="drawing" width="100%" height="100%"/>
</p>



## Mode collapse