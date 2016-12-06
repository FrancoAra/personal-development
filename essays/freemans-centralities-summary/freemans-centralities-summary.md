# Freeman's Centralities Summary

_This is a summary of the exelent work of Linton C. Freeman in the article [Centrality in Social Networks Conceptual Clarification](http://moreno.ss.uci.edu/27.pdf), where he explains the 3 main centralities applied to social network analysis._<!--more-->

(a) Degree Centrality
---------------------
_The degree of a point $p_i$ is simply the count of the number of other points, $p_j (i \ne j)$, that are adjacent to it and with which it is, therefore, in direct contact._ [4]

(a.1) **Degree**

* According to [3].
* _"Count of the number of adjacencies for a point $p_k$"_
* Where $a(p_i,p_k) = 1$ if and only if $p_i$ and $p_k$ are connected by a line, $0$ otherwise.

$$ C_D(p_k)= \sum_{i=1}^{n} a(p_i,p_k) $$

(a.2) **Relative Degree Centrality**

* According to [4].
* For a non-reflexive undirected graph.
* Where $n-1$ is the maximum of $C_D(p_k)$, in other words, the maximum amount of adjacent points a given point $p_k$ can have.

$$ C'_D(p_k)= \frac{ \sum_{i=1}^{n} a(p_i,p_k) }{ n-1 } $$

(b) Betweenness Centrality
-------------------------
_Betweeness is equal to the number of shortest paths from all vertices to all others that pass through that node._

(b.1) **Betweenness**

* According to [1] and [2].
* Where $ \sigma(i,j) $ is the count of shortest chains between $i$ and $j$.
* Where $ \sigma(i,u,j) $ is the count of shortest chains between $i$ and $j$ passing by $u$.

$$ \forall i \ne u \ne j , \sigma(i,u,j)<0, Iu = \sum_{(i,j)} \frac{\sigma(i,u,j)}{\sigma(i,j)} $$

(b.2) **Potential Betweenness**

* According to [4].
* For $ p_i \ne p_j $ and where there is at least 1 geodesic linking both points.
* Where $ g_{ij} $ is the number of geodesics linking $ p_i $ and $ p_j $.
* The probability of using any one of those is:

$$ \frac{1}{g_{ij}} $$

(b.3) **Potential of Control in Betweenness**

* According to [4].
* The potential of point $p_k$ for control of information passing between $p_i$ and $p_j$.
* Where $ g_{ij}(p_k) = $ the number of geodesics linking $p_i$ and $p_j$ that contain $p_k$.

$$ b_{ij}(p_k) = \frac{1}{g_{ij}} \times g_{ij}(p_k) = \frac{g_{ij}(p_k)}{g_{ij}} $$

_Is the probability we seek; it is the probability that point $p_k$ falls on a randomly selected geodesic linking $p_i$ to $p_j$_ [4].

(b.4) **Betweenness Centrality**

* Same as (b.1) but explained with (b.2) and (b.3).
* _To determine the overall centrality of a point $p_k$, we sum its partial betweenness values for all unordered pairs of points_ [4].
* Where $ i \ne j \ne k $.
* Where $ i < j $
* Where $n$ is the number of points in the graph.

$$ C_B(p_k) = \sum_i^n \sum_j^n b_{ij}(p_k) $$

(b.5) **Relative Betweenness Centrality**

* According to [4] the maximum value taken by $C_B(p_k)$ is achieved only by the central point in a star. It is:

$$ \frac{n^2 - 3n+2}{2} $$

* Therefore, the relative centrality of any point in the graph may be expressed as a ratio.

$$ C’_B(p_k) = \frac{2C_B(p_k)}{n^2 - 3n+2} $$

* Values of $C’_B(p_k)$ may be compared between graphs. A star or wheel, for example, of any size will have a center point with $C’_B(p_k) = 1$; all other points will yield $C’_B(p_k) = 0$.

(c) Closeness Centrality
----------------------
Is the average size of geodesics of one node to the rest of the nodes in the graph.

(c.1) **Closeness**

* According to [4].
* Where $d(p_i,p_k) = $ the number of edges in the geodesic linking $p_i$ and $p_k$.
* Where $n$ is the number of points in the graph.

$$ C_C(p_k) = \frac{\sum^n_{i=1} d(p_i, p_k)}{n-1} $$

References
----------
[1] L. Freeman, "A set of measures of centrality based on betweenness." Sociometry, vol. 40, pp. 35–41, 1977.

[2] M. Newman, "A measure of betweenness centrality based on random
walks," Social Networks, vol. 27, no. 1, pp. 39 – 54, 2005.

[3] J. Nieminen, "On centrality in a graph" Scandinavian Journal of Psychology, 15:322-336, 1974.

[4] L. Freeman, "Centrality in Social Networks Conceptual Clarification" Social Networks, pp. 215-239, 1979.
