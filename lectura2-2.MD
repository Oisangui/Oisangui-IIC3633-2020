# Commentary on BPR: Bayesian Personalized Rating from Implicit Feedback

In this paper they provide not a model, but an optimization criteria and algorithm for implicit feedback recommendation systems that generates better-quality recommendations than the other approaches available at the time. At first instance it is applyable into KNN and MF models to great success.

Their BPR-OPT optimization criterion is based on a bayesian approach to pairs of items, while the learning is done by their algorithm LearnBPR.

The novelty in this approach is that while the usual approach is to predict a personalized score based on a preference, they provide a different approach by using item pairs as training data, and then creating a *total order* of preference for each user according to the output of the optimization method.

They also give a comparison between this method and the combination of model-optimization of the method provided by Hu et al., stating that BPR-OPT is better. 

They don't analize the difference in performance between the two approaches, where the WR-MF method performs in linear time and the BPR-OPT does not, but with a less numerous sample, so there is a need for a thorough analysis on this side of the comparison. Another thing to critizise of their comparison is the fact that it is not known whether they input the values to the WR-MF method as binary or as the sum of the interactions between certain user and certain item as it should be, so more experiments are needed in this side also.
