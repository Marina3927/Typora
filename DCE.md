**0628**

https://www.kaggle.com/datasets/sheenabatra/facebook-data/code

https://developers.facebook.com/docs/graph-api/overview



**0605**

graph neural network (GNN) and reinforcement learning (RL)

**0507**

本周我学习了关于IM的survey，了解到IM是NP-hard问题，IM algorithm分为simulation-based,proxy-based,and sketch-based approach，传播模型分为progressive和non-progressive两种，代表性的模型是independent cascade model, linear threshold model, triggering model, LC，LT model分别是TR，CT model的特例，学习了monte carlo simulation-based algorithm。

**0515**

Partition, intersection = $\empty$, union = all

##### (in polynomial time)P, NP(exist), #P(num)

##### IM problem

Given a Graph $G(V,E)$, Budget k.

Find a k-seed set to maximize influence over G, denoted as (seed 初始种子节点)

$S=argmax_{S\subset V,|S|=k}\sigma(S)$ (S是激活的节点数)

Process: compare all possible $C_n^k$ k-seed sets

 Let $S^*=argmax_{S\subset V,|S|=k}\sigma(S)$ be the set maximizing *σ*(*S*) among all sets with size at most *k*. If the influence function *σ*(*·*) is monotone and submodular and *σ*(*∅*) = 0, then for the set $Sˆ*$ returned by GREEDY(*k*,*σ*) of Algorithm 1, we have:

$σ(S^*) ≥  1 − (1 − 1/k )^k σ(S^*)$

LT model: each node chooses a threshold uniformly at random [0, 1], become active if the total weight of its active neighbors is more than its threshold.

IC model: one active node is given a single chanve to activate its neighbor, attempts are independent.

### Algorithm

#### Monte Carlo (MC) simulations

Averaging results of a large number of simulations, relying on repeated random sampling

Estimating $\sigma(S)$

Pros: model generality

Cons: computational efficiency

**Basic Framework**

Start from *S* *∪ {**u**}* in *G*, simulates the activation process wrt. the corresponding diffusion model, and outputs the number of activated users  *I*(*S* *∪ {**u**}*). 

For each *S* *∪ {**u**}*, the algorithm runs *r* rounds and takes the average *I*(*S* *∪ {**u**}*) as an estimation of influence spread *σ*(*S* *∪ {**u**}*).

It iteratively selects a node *u* into *S* if *u* provides the maximum marginal gain.

**Reducing number of MC simulations**

TO estimate an *upper bound* of influence spread *S* *∪ {**u**}* in order to prune the ones with insignificant influences, which is $\delta(u|S_i)$ 

**Reducing number of MC simulations**

Community based Greedy algorithm (CGA), local subgraphs.

##### RR-sets

- reverse

- list all possibilities of A's influences
- find the overlapped ratio

###### Basic Greedy algorithm: nonnegative, submodular, monotone $\omicron(kmnR)$

marginal gain of node $v=\sigma(S\cup{v})-\sigma(S) $

running time: Basic Greedy > CELF > CELF++ > Static Greedy

VS. (exploiting submodularity)

###### CELF = cost effective lazy forward scheme

marginal gain in influence spread decreases. improve running time;

influence estimation function $(\sigma,(.) )$

###### CELF++

submodularity of social influence function, faster than CELF, a table $ <u.mg1, u.prev best, u.mg2, u.flag>$

*u.prev best* is the node with the maximum marginal gain among the users scanned till now in the current iteration; *u.mg*2 is the marginal gain in *σ*(*.*) for *u* with respect to the *S ∪ {**prev best**}* and *u.flag* is the iteration number, when *u.mg*1 was last updated. 

###### CB_IM = Community-based IM 

only the nodes in the same community are re-evaluated

###### PB_IM = Path-based IM

THe influence spread of a node v is estimated by 

$\sigma(v)=1+\sum_{u\in{O_v}}\sigma^u(v)$ set of nodes reachable, influence of v on u



command+, opens the preference window



