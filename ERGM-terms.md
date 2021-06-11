# ERGM terms
This file provides information about some more often used ERGM terms.
* __nodecov__
  * __Description:__ This term is useful when we want to knpw whether continuous node attributes affect tie formation.  
    This term adds sum of attr(i) + attr(j) to the network statistics for each edge (i, j).
  * __Important Notes:__
    * This term can be used for both directed and undirected networks, the value is equal to nodeocov + nodeicov for directed networks.
    * The attr argument must be a continuous node covariate.    
  * __Example:__
    * In a children relations network, we want to check whether being older affects the probability of friendship formation.  
      In other words, the probability that older children have a tendency for more friends.
  * __Usage:__ `nodecov(attr)`
* __nodefactor__
  * __Description:__ This term is useful when we want to know whether categorical node attributes affect tie formation.  
    For each unique category, it adds a network statistic. This statistic contains the number of times this value appeared in network edges.
  * __Example:__
    * In a citation network, we want to determine if being in a specific industry affects tie formation.
  * __Usage:__ `nodefactor(attr)`
