# Feature Engineering

Collection of resources and notes on Feature Engineering. 

Establishing a baseline: before starting feature engineering, it's a good idea to train a model on the data "as is", without feature engineering, to get a baseline to compare new models with. 

The second step to feature engineering should be to construct a ranking of features, with a **feature utility metric**, which measures associates between a feature and the target. <br>
There a many metrics, one of which is **correlation**, another one is **mutual information**. <br>
Mutual Information can detect **any** type of relationship, while **correlation only detects linear relationships**. <br>

> Mutual information describes relationships in terms of uncertainty. <br>
> The mutual information (MI) between two quantities is a measure of the extent to which knowledge of one quantity reduces uncertainty about the other.

You can see a good example and explanation of Mutual Information [here](https://www.kaggle.com/code/ryanholbrook/mutual-information/tutorial). <br>

Mutual Information is a logarithmic quantity. <br>
The least possible mutual information between quantities is 0.0. When MI is zero, the **quantities are independent**: neither can tell you anything about the other. <br>
Conversely, in theory there's no upper bound to what MI can be. In practice though **values above 2.0** or so are **uncommon**.

# Index



---
### Appendix A: Syllabus
Collection of terms and concepts as a quick memory refresher. 

### Appendix B: Resources
The following resources are the ones I've used: 
 * [Kaggle: Feature engineering Course](https://www.kaggle.com/code/ryanholbrook/what-is-feature-engineering)