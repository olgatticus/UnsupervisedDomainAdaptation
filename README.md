#  Unsupervised Domain Adaptation through Geodesic Distance Minimization & Pseudo-Labeling Refinement Steps 


Final project for the *Deep Learning* course at University of Trento (M.Sc. Artificial Intelligence Systems).

## Description

For our project we developed and implemented an Unsupervised Domain Adaptation method by putting together, integrating and adapting some procedures and ideas described in some papers that we found particularly interesting.

<br/>

In particular, we took inspiration from these publications:

[[1](https://arxiv.org/abs/2105.02089)] Y. Zhang and B. Davison:  "*Deep Spherical Manifold Gaussian Kernel for Unsupervised Domain Adaptation*", 2021 IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW), Nashville, TN, USA, 2021 pp. 4438-4447.

[[2](https://arxiv.org/abs/1707.09842)] Wang, Yifei & Li, Wen & Dai, Dengxin & Van Gool, Luc: "*Deep Domain Adaptation by Geodesic Distance Minimization*", EHT Zurich, 2017. 

[[3](https://arxiv.org/abs/1705.08180)] Morerio, Pietro & Murino, Vittorio: "*Correlation Alignment by Riemannian Metric for Domain Adaptation*", Istituto Italiano di Tecnologia, 2017. 

<br/>

Our method was mainly influenced by [1] for what concerns the general framework, the architecture of the network, the structure of the training procedure, the idea of performing pseudo-labeling refinement steps and the definition of a global loss as a sum of four different cost functions.

At first, we entirely adopted the method described in the aforementioned paper, although with many adjustments for those points that could be improved in some way or that were not clearly explained and hence needed a proper interpretation and adaptation in order to be implemented coherently. In this way we obtained an UDA framework that worked quite well, but that was not satisfactory enough.

For this reason, we decided to try and obtain better results by re-defining two of the cost functions that contribute to the global loss in [1]. Their contribution regards the measure of the discrepancy between the source and target domain distributions, at domain level and categorical level. In particular, it seemed to us that the definition of the so called Gaussian Kernel geodesic loss did not fully exploit the information of the first and second order statistics of the domains' distribution. Therefore, we substituted it with an alternative geodesic loss taking inspiration from some ideas put forward in [2] and [3], with the aim of properly capturing and reducing the domains disalignment, in terms of both first order and second order statistics.
