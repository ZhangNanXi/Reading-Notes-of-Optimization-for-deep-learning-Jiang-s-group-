# Reading-Notes-of-Optimization-for-deep-learning-Jiang-s-group-
This is a reading notes of the paper [Sun, Ruoyu. "Optimization for deep learning: theory and algorithms." arXiv preprint arXiv:1912.08957 (2019). ]
# Reading notes of Ruoyu Sun's paper
## Introduction
Some definitions reviewed:
### Lipschitz const on Neural networks
Deep neural networks are known for being very sensitive to their input, and adversarial examples provide a good illustration of their lack of robustness  Indeed, a well-chosen small perturbation of the input image can mislead a neural network and significantly decrease its classification accuracy. One metric to assess the robustness of neural networks to small perturbations is the Lipschitz constant (see Definition 1), which upper bounds the relationship between input perturbation and output variation for a given distance.
Intuitively, a Lipschitz continuous function is limited in how fast it can change: there exists a real number such that, for every pair of points on the graph of this function, the absolute value of the slope of the line connecting them is not greater than this real number; the smallest such bound is called the Lipschitz constant of the function.
Recently, Lipschitz continuity was used in order to improve the state-of-the-art in several deep learning topics: (1) for robust learning, avoiding adversarial attacks was achieved in  by constraining local Lipschitz constants in neural networks. (2) For generative models, using spectral normalization on each layer allowed  to successfully train a GAN on ILRSVRC2012 dataset. (3) In deep learning theory, novel generalization bounds critically rely on the Lipschitz constant of the neural network.
Even for 2-layer Multi-Layer-Perceptrons (MLP), NP-hard.
Multiple techniques are developed to upper bound the Lip const.
Ref:
  1. Lipschitz regularity of deep neural networks:
analysis and efficient estimation
## Normalization Trick 
Understanding Batch Normalization, eg.
![](2020-03-07-14-36-02.png)
###  The benefits of BN
- Higher learning rates.
- More robust to changes to hidden layers.
- Reduce the amount of the covariate shift in hidden layer. $W$ value in each layer is more stable so the next layer has a rock to stand on. Input changes, it changes less.
- Regularazation effect: each input batch is normalized on each mini-batch and has noise introduced. So by subtracting the mean the noise of that batch, it is adding noise in each layer's activations just like dropout.(slight). By using a larger mini-batch size, you reduce the regularization effect.(https://www.youtube.com/watch?v=nUUqwaxLnWs)
## Skip Connection
- Problem: as the network goes deeper and deeper, the performance of nn on training set gets worse. 
- Skip connection helps the layer to learn identity matrix so it guarantees that it least does not get worse.  Sometimes you get lucky and get bettern results. (The skip layer's input and output are of same dimension.https://www.youtube.com/watch?v=Qoz1KCfPtBk)
## Gradient Descent Method
For intuitive understanding of variants of GD:
https://ruder.io/optimizing-gradient-descent/ gives a thorough summarize.
Convergence Proof: open problem
Current progress: convergence reusults on some special networks under specified conditions.
Reference paper: on the convergence of a class of adam-type algorithms for non-convex optimization.



