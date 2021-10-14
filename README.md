# unsupervised_anomaly_detection

## Existing approaches 

We can classify the existing approaches for "unsupervised" anomaly/outlier detection based on (at least) two criterias:

- The "contamination" of the training dataset

    Based on this criteria, each approach will assume one of the following:

    - Contaminated dataset: the training dataset contains both normal and anamolous elements. 
    - Uncontaminated dataset: The training dataset contains only normal samples. The methods that take this assumption are also refered weakly supervised approaches.

- How far is the distribution of the anomalous samples to the normal samples

<p align="center">
<img src="assets/datasets.JPG" alt="drawing" width="80%" height="50%"/>
</p>

     - If the anamolous samples lie far away from the normal distribution (as shown in (b)), the problem is known is as out of distribution detection (OoDD) . Note that OoDD is sometimes refered as a seperate problem and not included in the family of anomaly deteion, but here I will assume that the OoDD detection problem lies under the anomaly detection umberlla.

     - On the other hand, if  the anamolous samples lie at the boundaries of normal distribution (as shown in (b)), the problem is known is as fault detection (FD)

For the problem of fault detection, the image can be also segmented and the while this can be for the out of disribution detection.

Note that to the best of my knowledge, there is no existing approach that tackles the problem of fault detection assuming a contaminated dataset.

## UFDGAN 
#### Assumptions: 
- Contaminated training set 
- The fault percentage is known

#### Why based on the unsupervised contrastive learning will not work?

The dataset is composed of multi modal data, but only one mode is labaled as anomaly. If the dataset is to a human, he will not be able to the anomaly exactly.
For that, the 

<p align="center">
<img src="assets/training_samples.JPG" alt="drawing" width="100%" height="100%"/>
</p>

So, I argue that the problem of unsupervised fault detection assuming a contaminated training dataset is challenging even for a human being . To guarantee the , the training dataset is only composed of two salient modes.  

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

