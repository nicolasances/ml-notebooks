# ML Strategy
Summary of strategies to traing and tune models. 

## The Knobs to turn
It is important to know what knobs to tweak based on the phase of the model development. 

These are the step-by-step objectives and what Andrew Ng tweaks in these phases: 

1. Training - You want to fit well the training set.<br>
In this phase you will tweak: 
    * Size of the network (bigger network for better training performance)
    * Optimizer (e.g. Adam)
    * Some hyperparameters

2. Cross-Validation - You want to fit well the **dev (CV)** set.<br>
In this phase you will tweak: 
    * Regularization Hyperparameters
    * Bigger **training** set 

3. Test - You want to fit well the **test** set.<br>
In this phase you will tweak: 
    * Bigger **dev** set

4. Live - You want to perform well on live examples.<br>
If you see problems in this phase, you should: 
    * Change the **dev** set
    * Change the cost function