---
tags:
  - Fluids
---
# K-factors for gradual contraction and enlargement

The publication _Flow of fluids through valves, fittings, and pipe_ (Crane)[^1] is the bible of hydraulics, and many of us use it daily for pressure drop calculations. It’s probably worked into the templates you’ve used a thousand times. More than likely however there has been some simplification and your tool probably assumes you are using sudden enlargements/reducers. This is more conservative in terms of frictional pressure loss of course, but it situations where we want to be more accurate we can start to look at the angle of divergence.

[^1]: Technical paper 410M ([Crane's website](https://tp410.com/))

Here is a brief extract from the Crane method on calculation of K-factor for gradual enlargement/reduction:

![[Crane1.png]]

>[!info]
>Where subscript 1 for diameter indicates the smaller diameter, and 2 the larger diameter.

To determine K-factor we are required to calculate the angle of divergence $\theta$. If like me you only had the internal dimensions of the fitting available, then let me save you some time. From known upstream diameter, downstream diameter and reducer length $L$, the angle of divergence is given below.

![[Kfactors.png]]

 $$x=\frac{d_{2}-d_{1}}{2}$$
 >[!info] Angle of divergence
$$\theta=2\tan^{-1}\left ( \frac{d_{2}-d_{1}}{2L} \right )$$

 >[!info] Re-arranged to find reducer length
$$L=\frac{d_{2}-d_{1}}{2\tan \left ( \frac{\theta}{2} \right )}$$
