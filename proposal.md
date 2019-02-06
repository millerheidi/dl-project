# Implementing Convolutional Neural Networks on Photonic Hardware
Heidi Miller
6 Feb. 2019
## Summary of Silicon Neuromorphic Photonics
The goal of my group's [[research]](https://www.queensu.ca/physics/shastrilab/home) is to develop a way of implementing neuromorphic architecture in photonic (electro-optical) hardware. In the first lecture of CISC867, we discussed the limitations of hardware for doing deep learning. With increasing data sets, and demand for greater speeds and energy efficiencies, traditional electronic hardware is finding it tough to fit the bill, since quantum tunneling effects start to play a role when fabricating smaller and smaller transistors. Using silicon photonics (potentially 4 orders of magnitude faster and more energy efficient) as a hardware platform is advantageous because it is scalable, and integrating these silicon chips with CMOS would not require any new fabrication techniques. We have already [[experimentally demonstrated]](https://arxiv.org/abs/1812.11898) a silicon photonic modulator neuron, which can perform fan-in, inhibition, time-resolved processing, and autaptic cascadability.


## Summary of project
My ultimate goal is to program a Convolutional Neural Network (CNN) on the [[CIFAR]](https://www.cs.toronto.edu/~kriz/cifar.html) dataset, and use an algorithm that would be compatible with our hardware. If we are performing convolutions, it is feasible to have 32x32 neurons corresponding to each pixel in the 32x32 image, but a larger number of neurons may be difficult to implement on chip.

I have not yet decided which type of CNN to use, because it largely depends on which is most applicable for silicon photonics. For example, finding the maximum is difficult to implement in solely silicon photonics, but summing multiple signals at once is very easily implemented with two photodiodes (optical to electrical converter). This would make average-pooling much easier than max-pooling. It could potentially be [[better]](https://arxiv.org/abs/1412.6806) to use no pooling at all. At first glance, an All-CNN might be the network of choice.

We must take advantage of the fact that our hardware will be must faster, so we are aiming for an algorithm that trades time for accuracy.

Therefore, the "comparison" machine learning algorithm (another CNN) will be one that is very similar to the one we will use for photonics, and we will analyze the tradeoffs (e.g. speed/accuracy) that arise when implementing photonics.

The final submission will contain the (1) CNN we intend to use for photonics, (2) a similar CNN architecture comparison, (3) the photonic hardware implementation, and (4) energy and speed calculations for our photonic hardware architecture applied to this problem.
