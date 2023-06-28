# Proxy-Based Algorithm

## Influence Ranking Proxy

### DEGDIS

based on the degree proxy

The influence scores of u’s neighbors are discounted by a factor to account for the influence overlaps.

The influence of u will be subtracted by 1 if u is a neighbor of v.

### Group-PageRank - GPR(S)

= the sum of the PageRank scores of all nodes in S with a
“discount” for the mutual influences between the nodes
in S. 

an upper bound estimation of the influence of S under the IC mode

Linear (power iteration) / Bound (directly)

### -> IRIE - Influence Ranking Influence Estimation

the influence r(u) of a node u comprises its influence to itself, i.e, 1, and the sum of the influences it propagates to all its neighbors

$r(u) = (1 − AP_S(u))(1 + α \sum _{v\in N^{out}_u}P_{uv}r(v))$

### SPIN

All the users in G are ranked by their **Shapley values** in a non-increasing order, and the algorithm iteratively adds the
top-ranked one which is not adjacent to any node in S to S
until k users are chosen. 

### IMRANK

Last-to-First Allocating (LFA) strategy to estimate the marginal influence ∆r(vri) of each node wrt. ranking r.

## Diffusion Model Reduction Proxy

specific for only one model (LC, IT)

### IC Model Reduction Proxy

#### Shortest-Path Model

S has only one chance to activate v in step d(S, v).

#### SP1M

in steps d(S, v) and d(S, v)+ 1

intersection: monotone and submodular, the greedy framework guarantee a (1 − 1/e)  approximate solution under
both proxy models. Fail when the edge probabilities are neither constant nor small, b/c the influence between two nodes is small and sensitive.

#### MIA (arborescence树木园) / PMIA - prefix exclusing MIA

maximum influence paths MIP (u, v) (all paths)

Construct:  a maximum influence in-arborescence MIIA(v, θ) 
containing all MIPs ended with v 
with propagation probabilities at least θ and 
a maximum influence out-arborescence MIOA(v, θ) 
containing all MIPs started from v with propagation probabilities at least θ for each node v $\in$ V

Drawback: not be scalable if the graph is dense and the edge
propagation probabilities are not small

#### IPA - independent path algorithm

prune path w. pp less than a given threshold

Drawback: degrade the quality of seeds

### IT Model Reduction Proxy

#### LDAG

restricts the influence graph to be a DAG (directed acyclic graphs).

#### SIMPATH

Influence <- by enumerating all simple paths 

#### EASYIM

higher accuracy: accounts for the overlaps between different paths  