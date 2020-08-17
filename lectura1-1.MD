## Commentary on Item-based collaborative filtering recommendation algorithms by Sarwar et al.

*Ignacio Loyola*

This paper explains a new approach of tackling the challenge of providing the millions of users of sites with hundreds of thousands of items with accurate recommendations at a minimum computation cost using item-based collaborative filtering recommendation systems. This new approach consists of using a much smaller number of items than available, namely, the top k items by similarity to each item, where k is defined to be the model size, thus the space complexity of storing all similarities would be O(n * k) which is much smaller and convenient than O(n * n).


Although the results are promising and are a sort of proof of the effectiveness of the approach, I have some reservations with respect to the theory and the experimentation.  

Starting by the theory the similarity formulas don't really take into consideration the fact that many items i and j could have only one or a limited number users which rate them both, thus when we compute the similarity of an item i to an item j with only one user in common, the similarity will be biased and not accurately represented. This problem is mentioned by Schafer et al., who suggests either discarding, adjusting similarity to 0 or using probability to incorporate a prior belief. I suggest multiplying by a modified version of the sigmoid function shifted to the right (as sigmoid functions seem to be very practical as exemplified by its use in FunkSVD), which takes as argument the number of users who rate the combination i,j; for small values, it would give values closer to 0, and after a certain threshold it would give almost 1.


Another problem is the fact that a k size of the model too small could produce items for whom the current user has no rating, thus rendering the recommendation not feasible in that case.


Finally, on the experimental side of things, the dataset is not realistic according to either size or shape of possible real life datasets because in reality there are overwhelmingly more users than items, whereas in this paper the dataset described has the opposite shape, with more items than users. 


I conclude that more experiments must be realized with realistically shaped datasets, but also taking into consideration the possible problems that I have stated.

### References

Schafer J.B., Frankowski D., Herlocker J., Sen S. (2007) Collaborative Filtering Recommender Systems. In: Brusilovsky P., Kobsa A., Nejdl W. (eds) The Adaptive Web. Lecture Notes in Computer Science, vol 4321. Springer, Berlin, Heidelberg. https://doi.org/10.1007/978-3-540-72079-9_9
