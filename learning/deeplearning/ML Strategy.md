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

## Training, Dev, Test set sizes
In traditional ML, you would apply a split of around 60% train, 20% dev, 20% test. <br>
In Deep Learning, where a lot of data is used, you will be fine using 98% train, 1% dev, 1% test.<br>That is because even 1% is a huge amount of records when considering the amount of data needed by a DL model.

## Other

Andrew Ng recommends, when comparing models, to consider only **one evaluation metric** (or at least to boil down to a single one used for comparison). *He makes the example of using F1 score instead of Precision and Recall* and, in case of multiclass classification, instead of comparing the F1 score of each class, to average the F1 scores. 

