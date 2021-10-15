# unsupervised_anomaly_detection

## Existing Approaches 

We can classify the existing approaches for "unsupervised" anomaly/outlier detection based on (at least) two criterias:

- The "contamination" of the training dataset

    Based on this criteria, each approach will assume one of the following:

    - Contaminated dataset: the training dataset contains both normal and anamolous elements. 
    - Uncontaminated dataset: The training dataset contains only normal samples. Such approach is also refered as weakly supervised.

- How far is the distribution of the anomalous samples to the normal samples

    - If the anamolous samples lie far away from the normal distribution (as shown in (b)), the problem is known is as out of distribution detection (OoDD) . Note that OoDD is sometimes refered as a seperate problem and not included in the family of anomaly deteion, but here I will assume that the OoDD detection problem lies under the anomaly detection umberlla.

    - On the other hand, if  the anamolous samples lie at the boundaries of normal distribution (as shown in (b)), I will refer to the problem as fault detection (FD).
<p align="center">
<img src="assets/datasets.JPG" alt="drawing" width="80%" height="50%"/>
</p>

Note that to the best of my knowledge, there is no existing approach that tackles the problem of fault detection(FD) assuming a contaminated dataset.

## UFDGAN 
#### Assumptions: 
- Contaminated training set 
- Fault detection (not OoDD)
- The fault percentage is known

#### Why the problem is quasi unsolvoble even for a human?
let's take the MTSD dataset as an example. As shown in the figure bellow,
- (a) is a sample of the majority normal samples
- (b) is a sample of a minority within the normal data 
- (c) is a sample of a the faulty data (also a minority)

So, the dataset is composed of multi modal data, but only one mode is labaled as anomaly. 

If the dataset is handed to a human, he most likely will not be able to correctly detect the anomalous samples.

<p align="center">
<img src="assets/training_samples.JPG" alt="drawing" width="100%" height="100%"/>
</p>

So, I argue that the problem of unsupervised fault detection assuming a contaminated training dataset is challenging even for a human being. And in order to be solvoble, the data distribution should be exactly a mixture of ONLY two salient modes, which may rarely be the case in the real world.

