### GWESP metric

There are different metrics and statistics you can use to measure different local and global statistics modeled with ERGM. One of these statistics involve measuring the effect of triads and transitivity in the network. One of the terms included in `ergm-terms` is the triangles which counts the number of triangles in the network. The issue with this model is that with networks having lots of triangles of this kind, the MCMC algorithm tends to learn to prefer networks with counts of triangles much more higher than the observed network. To address this problem we can turn into `EWSPs`. Thanks to the decay parameter in this statistic, we can control and confine the model in terms of prefering the networks with higher number of triangles.

The statistic is defined as follows: 


<img style="background-color:white;padding:10px;" src="https://render.githubusercontent.com/render/math?math=w=e^\alpha\sum_{i = 1}^{n - 2}{[1 - (1 - e^{-\alpha})^i]p_i}">


In the equation above, n denotes the number of nodes, pi denotes the number of triads having i ESPs. As the maximum number of ESP counts is `n-2`, the summation goes to that extent. This statistic works like other statistc in ERGM. By adding one tie, we count the number of triangles that would be closed and also the number of trianlges that would be removed, and so, we compute the change statistic in a similar fashion to other `ergm-terms`. 

The decay parameter works in the way that in higher numbers of ESP counts, the probability of observing networks as such would decrease. In other words, the probability of a tie that closes a triangle where nodes in the triangle already have shared partners is less than the probability of a tie that closes a triangle among nodes that previously had no edgewise shared partners. As the number of existing edgewise shared partners among nodes in the triangle to be closed increases, the change statistic for closing this triangle will continue to decrease. This is the feature of GWESP that allows it to model transitivity without the degeneracy problems of the triangle term!


