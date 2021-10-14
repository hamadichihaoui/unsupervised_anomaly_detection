# unsupervised_anomaly_detection

## Existing approaches 

We can classify the existing approaches for "unsupervised" anomaly detection based on (at least) two criterias:

- The "contamination" of the training dataset

    Based on this criteria, each approach will assume one of the following:

    - Contaminated dataset: the training dataset contains both normal and anamolous elements. 
    - Uncontaminated dataset: The training dataset contains only normal samples. The methods that take this assumption are also refered weakly supervised approaches.

- How far is the distribution of the anomalous samples to the normal samples

<p align="center">
<img src="assets/datasets.JPG" alt="drawing" width="80%" height="50%"/>
</p>
the anamolous samples  lie far away from the training distribution, is known is as out of distribution detection (OoD)

Based on the type of the dataset we, out of distribution detection (OoD) and fault detection (FD).
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



## Out Of Distribution Detection through GAN's Mode Collapse

We adopt the same assumptions as the UFDGAN paper, but we tackle the problem of Out OF Distribution detection.

#### Recent Related Work
 [SSD: A unified framework for selfsupervised outlier detection.](https://arxiv.org/pdf/2103.12051.pdf).  

[CSI: Novelty Detection via Contrastive Learning on Distributionally Shifted Instances.](https://arxiv.org/pdf/2007.08176.pdf)

#### Approach
The model is composed of a GAN (generator and a discriminator), along with an encoder. and the encoder tries to learn the reverse mapping from the image space to the gan's latent space. After each iteration, based on the reconstruction error, the is filtered out. 
<p align="center">
<img src="assets/model.JPG" alt="drawing" width="50%" height="50%"/>
</p>

### Dataset
The MNIST dataset is used. The 0 is used as the normal and sampled from the different orher classes. the anomaly percentage is 5%.

