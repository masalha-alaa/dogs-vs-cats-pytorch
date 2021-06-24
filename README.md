# Dogs vs. Cats Classification using CNN

In this Kaggle competition, the mission is to classify images of dogs and cats.
The evaluation metric is the log loss function:

![image](https://user-images.githubusercontent.com/78589884/122687982-32ec4c80-d222-11eb-838e-61e7c7bc357f.png)

where
* n is the number of images.
* ŷ<sub>i</sub> is **the predicted probability of the image being a dog**.
* y<sub>i</sub> is 1 if the image is a dog, 0 if cat.

My goal in this notebook was **not** to achieve a high accuracy (as I could do that simply by using a pretrained model from PyTorch), but to experiment with CNNs and building a deep neural network in PyTorch, as well as to work with a database not preloaded by PyTorch (unlike [my work with MNIST](https://github.com/masalha-alaa/mnist-pytorch)).

Using this model I achieved 87% accuracy and 0.26 loss on the validation set, and 0.32 loss on the test set.

The model's network mainly consists of 3 convolution layers and 2 fully connnected layers, but for more details please find the notebook [cats-vs-dogs-redux.ipynb](https://github.com/masalha-alaa/dogs-vs-cats-pytorch/blob/master/cats-vs-dogs-redux.ipynb) in the root directory (refresh if it doesn't load), in which you'll find a complete walkthrough of this work, or head over to my [Kaggle profile](https://www.kaggle.com/alaamasalha/cats-vs-dogs-redux) where you'll find the same notebook and see some of my other projects.

![image](https://user-images.githubusercontent.com/78589884/122798911-cc226e00-d2c9-11eb-9e00-d793860daee8.png)

---

Notes:
After implementing this network, I have read the [AlexNet paper](https://www.cs.toronto.edu/~hinton/absps/imagenet.pdf), and in hindsight I would make a few changes to my network:
* Aspect ratio should be maintained when resizing the images (i.e. resize such that the shorter edge = `X`, and then crop the center).
* Input normalization should be applied only on the training set. That might be the rason why my accuracy and loss charts strongly fluctuated when I normalized the validation and test sets in addition to the training set. However, I ended up disabling input normalization altogether because of these fluctuations.
* Larger (more broad) fully connected layers at the end (would take a longer time to train, but seems to be worthy).
* Data Augmentation: Being very beneficial and easy to implement in PyTorch, I should have definitely used this tool for the sake of generalization.
