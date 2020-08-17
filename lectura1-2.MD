


# FunkSVD Commentary

*Ignacio Loyola*


The author embarked on the task of predicting the ratings of a *very* sparse matrix of users-items, specifically, eighty five empty cells for each given rating. His attack on the problem can be separated in two parts, the first, which involved calculating the average rating offset for every user taking into consideration the users which may have very little ratings and the expectation of what might be in the black spaces, and the second, which has to do with modelling the problem to make it more simple by applying singular value decomposition (SVD). These two aspects of the problem are not really that separated, though, because the expected value of blank spaces is computed to make the SVD return a better result, so we might say the central technique in use here is the way the problem is modelled using this SVD.



In summary, each user can be modelled as being able to recognize a number of features each movie has, and according to their own liking they are defined by how they rate each of these features, so the problem might be enormously simplified by this way of seeing the interaction between the user and the movie. And the way to implement this is by a singular value decomposition.


What shocks at first is the simplicity with which the author seems to tackle the problem of implementing such concept using approximations of the error in a sort of *backpropagation* to great success, and helped by offset adjusting and method to counter overfitting, it proved to be quite an effective approach.


What leaves me skeptical, though, is the need and opportunity to further exploit the idea behind the model. A certain user might or might not like certain features of a movie, but do they recognize this feature as the same as other users? If Star Wars is all-action to a user, it might not be the case to another, and a user might spot the action component of a certain movie but not in other. The score the user gives to a certain feature is something I am in accord with, but maybe one could consider the *obviousness* with which a user exhibits certain feature and the *sensitivity* certain user has for identifying those features. Why could this give us any improvement? Schafer et al. mentions that the users with more esoteric tastes are often *the most valuable* to recommeneder systems, thus if we can have an extra glimpse at the users with a more sensible and developed taste, then it just might prove to be a worthy undertaking.


### References

Schafer J.B., Frankowski D., Herlocker J., Sen S. (2007) Collaborative Filtering Recommender Systems. In: Brusilovsky P., Kobsa A., Nejdl W. (eds) The Adaptive Web. Lecture Notes in Computer Science, vol 4321. Springer, Berlin, Heidelberg. https://doi.org/10.1007/978-3-540-72079-9_9
