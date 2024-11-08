# UAV Based Object Detection Using KAN Based VGG-11 and Prototypical Networks:

## Kolmogorov Arnold Representational Theorem : 
Every multivariate continuous function f:[0,1] n → R can be represented as a superposition of continuous single-variable functions.

## Kolmogorov Arnold Networks :
According to the original source : [Kolmogorov Arnold Networks by Ziming Liu, Yixuan Wang, Sachin Vaidya, Fabian Ruehle, James Halverson, Marin Soljačić, Thomas Y. Hou, Max Tegmark ](https://arxiv.org/abs/2404.19756)' It has learnable activation functions on edges ("weights"). KANs have no linear weights at all -- every weight parameter is replaced by a univariate function parametrized as a spline. We show that this seemingly simple change makes KANs outperform MLPs in terms of accuracy and interpretability. For accuracy, much smaller KANs can achieve comparable or better accuracy than much larger MLPs in data fitting and PDE solving. Theoretically and empirically, KANs possess faster neural scaling laws than MLPs. For interpretability, KANs can be intuitively visualized and can easily interact with human users. Through two examples in mathematics and physics, KANs are shown to be useful collaborators helping scientists (re)discover mathematical and physical laws. In summary, KANs are promising alternatives for MLPs, opening opportunities for further improving today's deep learning models which rely heavily on MLPs. 


## VGG-11 :
VGG (Visual Geometry Group) is a convolutional neural network architecture that was proposed by researchers from the University of Oxford in 2014. It gained popularity and recognition for its simplicity and effectiveness in image classification tasks, The VGG neural network architecture aims to address the challenge of image classification using deep convolutional neural networks. The primary focus of the VGG architecture is on increasing the depth of the network while using simple and uniform convolutional layers, whereas the number 11 represents the model having 8 convolutional layers and 3 fully connecting layer.

## prototypical networks:
Prototypical networks are based on the concept that there exists an embedding in which several points cluster around a single prototype representation for each class. It aims to learn per-class prototypes based on sample averaging in the feature space, To be more specific, prototypical networks compute each class’s M-dimensional representation or prototype through an embedding function with learnable parameters. Also, each prototype is the mean vector of the embedded support points belonging to its class.

## KAN Based VGG-11 with Prototypical Networks :
In this project we built a KAN Based VGG-11 Model using pytorch and [IvanDrokin's torch-KAN-Convs library](https://github.com/IvanDrokin/torch-conv-kan.git)

* The Train Directory contains the Training code, after training the checkpoints are saved into the checkpoints folder
* The Eval Directory contains the code for Evaluation using the checkpoint which achieved highest accuracy during training.
* The dataset folder contains the images sorted according to their classes (i.e. truck, bike, pedestrian, car).
* Don't forget to adjust the paths for dataset and checkpoints in the code before running.
* We used Google colab-pro with TPU-v2 to train the model, and T4 GPU to evaluate the model.
* The model takes roughly 9 hours to train the model with 10 epochs and 18 minutes to evaluate on 5 epochs.
* The model use upto 60 GB of RAM from TPU-v2 for training, and 14 GB of VRAM from T4 GPU to evaluate.
* We didnt train the model on Actual TPU hardware but we merely used TPU because of the memory limitations on google colab for CPU and GPU, in short we trained the model on cpu, so it took long time(~9 hrs) to train it.
* The dataset is roughly 3500 images combinedly.
* The KAN based VGG-11 didn't catchup with the accuracy of actual VGG-11 model(difference between accuracy is ~3%)
* But the KAN based VGG-11 model Converged faster on FSL methodology
* The interpretability of KAN based VGG-11 model is pretty high from the beginning, compared to the VGG-11 model.
* This makes KAN models better for FSL applications where data availability is low.

