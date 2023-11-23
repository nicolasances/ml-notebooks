# ML Strategy
Summary of strategies to traing and tune models. 

## The Knobs to turn
It is important to know what knobs to tweak based on the phase of the model development. 

These are the step-by-step objectives and what Andrew Ng tweaks in these phases: 

1. Training - You want to fit well the training set.<br>
In this phase you will tweak: 
    * Size of the network (bigger network for better training performance)
    * Train longer or Better Optimizer (e.g. Adam, to converge faster)
    * Some hyperparameters
    * Different NN Architecture

2. Cross-Validation - You want to fit well the **dev (CV)** set.<br>
In this phase you will tweak: 
    * Regularization Hyperparameters, Dropout
    * Data augmentation
    * Bigger **training** set (more data)

3. Test - You want to fit well the **test** set.<br>
In this phase you will tweak: 
    * Bigger **dev** set

4. Live - You want to perform well on live examples.<br>
If you see problems in this phase, you should: 
    * Change the **dev** set
    * Change the cost function

## Data Mismatch
In some cases, you will have two sets of data: easy-to-get data that you mostly train your model on (e.g. stock photos of cats) and more-rare data (e.g. uploads from mobile). <br>
Often you will want to put the more-rare data in the Dev and Test sets, to really test how robust your model is.<br>

In those cases you might end up with a (e.g.) 4% error on Training Set and 10% error on the Dev Set. <br>
In those cases, how do you know if you have high variance or if the difference is explained by the difference in the data distribution between Train and Dev sets? <br>
So in these cases what you would do, is split the training set into Training and Training-Dev set, so that you can see if you have high variance (Training-Dev error much higher than  Training error) or if the performance degradation is due to the difference in the data distribution of Training and Dev set (Training-Dev error similar to Training error, but both are much lower than Dev error). 

Note that in some cases **the Dev or Test errors will be lower than the Training error**. <br>
When that happens, you can deduce that the Dev and Test data is actually "simpler" than the Training data. By *easier* I mean that it's easier data to recognize for the machine. 

## Training, Dev, Test set sizes
In traditional ML, you would apply a split of around 60% train, 20% dev, 20% test. <br>
In Deep Learning, where a lot of data is used, you will be fine using 98% train, 1% dev, 1% test.<br>That is because even 1% is a huge amount of records when considering the amount of data needed by a DL model.

## Other

Andrew Ng recommends, when comparing models, to consider only **one evaluation metric** (or at least to boil down to a single one used for comparison). *He makes the example of using F1 score instead of Precision and Recall* and, in case of multiclass classification, instead of comparing the F1 score of each class, to average the F1 scores. 

