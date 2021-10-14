# unsupervised_anomaly_detection

## Existing approaches 

We can classify the current approaches for anomaly detection based on two 
- Degree of the supervision
    Based on the used dataset in the training dataset
    - Contaminated dataset: it contains both normal and anamolous elements in the training. 
    - Uncontaminated dataset: The training data contains only normal samples. The methods that take this assumption are also refered weakly supervised approaches.

- Type of the training dataset:
<p align="center">
<img src="assets/datasets.JPG" alt="drawing" width="50%" height="50%"/>
</p>
the anamolous samples  lie far away from the training distribution, is known is as out of distribution detection (OOD)

Based on the type of the dataset we, out of distribution detection (OOD) and fault detection (FD).
For the problem of fault detection, the image can be also segmented and the while this can be for the out of disribution detection.

There is no existing method that take contaminated dataset and tackles the problem of fault detection.

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



## Out Of Distribution Detection using Mode Collapse

We adopt the same assumptions as the UFDGAN paper, but we tackle the problem of Out OF Distribution detection.

#### Recent Related Work
 [SSD: A unified framework for selfsupervised outlier detection.](https://arxiv.org/pdf/2103.12051.pdf).  

[CSI: Novelty Detection via Contrastive Learning on Distributionally Shifted Instances.](https://arxiv.org/pdf/2007.08176.pdf)

#### Model

<p align="center">
<img src="assets/model.JPG" alt="drawing" width="50%" height="50%"/>
</p>

### Dataset