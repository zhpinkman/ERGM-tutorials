# ERGM terms
This file provides information about some more often used ERGM terms.
* __edges__
  * __Description:__ This term adds a network measure equal to the number of edges. It controls for the density of our model.
  * __Usage:__ `edges`

* __mutual__
  * __Description:__ It adds a network statistic equal to the number of pairs i and j for which (i,j) and (j,i) both exist.
  * __Important Notes:__
    * It can only be used with directed networks.
  * __Example:__
    *  In a citation network we want to check if citing and cited relations tend to occur at the same time.
  * __Usage:__ `mutual`

* __nodecov__
  * __Description:__ This term is useful when we want to know whether continuous node attributes affect tie formation.  
    This term adds sum of attr(i) + attr(j) to the network statistics for each edge (i, j).
  * __Important Notes:__
    * This term can be used for both directed and undirected networks, the value is equal to nodeocov + nodeicov for directed networks.
    * The attr argument must be a continuous node covariate.    
  * __Example:__
    * In a children relations network, we want to check whether being older affects the probability of friendship formation.  
      In other words, the probability that older children have a tendency for more friends.
  * __Usage:__ `nodecov(attr)`

* __nodeicov/nodeocov__
  * __Descritption:__ Same as nodecov but used for in-edges/out-edges.
  * __Important Notes:__
    * These terms may only be used with directed networks.
  * __Example:__
    * Let's assume we have a directed network of children fights; showing who attacked whom. We can use this term to check whether being older affects being attacked/attack more often.
  * __Usage:__ `nodeicov(attr)/nodeocov(attr)`

* __nodefactor__
  * __Description:__ This term is useful when we want to know whether categorical node attributes affect tie formation.  
    For each unique category, it adds a network statistic. This statistic contains the number of times this value appeared in network edges.
  * __Example:__
    * In a patent citation network, we want to determine if being in a specific industry affects tie formation.
  * __Usage:__ `nodefactor(attr)`

* __nodeifactor/nodeofactor__
  * __Description:__ Same as nodefactor but counts are calculeted based on in-edges/out-edges.
  * __Example:__
   * In the patent citation network, we want to know if patents industry of cited/citing affect tie formation.
  * __Usage:__ `nodeifactor(attr)/nodeofactor(attr)`

* __nodematch__
  * __Description:__ This term captures homophily on categorical attributes.
  * __Example:__
    * In a friendship network, we want to measure whether people have a tendency towards same-gender friendships.
  * __Usage:__ `nodematch(attr)`

* __absdiff__
  * __Description:__ This term captures absolute differences. It's somehow a homophily term for continuous variables.
  * __Important Notes:__
    * the `pow` argument can be used to specify the power of the absolute difference; default is one.
  * __Example:__
    * In a friendship network, we want to know whether having a small age difference affects friendship formation.
  * __Usage:__ `absdiff(attr, pow=1)`

Terms to add: triangle, edgecov, gwesp, degree, nodemix, diff, isolates, altkstar
