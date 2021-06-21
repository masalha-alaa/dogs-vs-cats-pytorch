# Dogs vs. Cats Classification using CNN

In this Kaggle competition, the mission is to classify images of dogs and cats.
The evaluation metric is the log loss function:

![image](https://user-images.githubusercontent.com/78589884/122687982-32ec4c80-d222-11eb-838e-61e7c7bc357f.png)

where
* n is the number of images.
* ŷ<sub>i</sub> is **the predicted probability of the image being a dog**.
* y<sub>i</sub> is 1 if the image is a dog, 0 if cat.

My goal in this notebook was **not** to achieve high accuracy (as I could do that simply by using a pretrained model from PyTorch), but to experiment with building a deep neural network in PyTorch (deeper than the one I built in [my MNIST notebook](https://github.com/masalha-alaa/mnist-pytorch)), as well as to work with a database not preloaded by PyTorch (unlike MNIST).

Using this model I achieved 90% accuracy and 0.26 loss on the validation set, and 0.33 loss on the test set.

Please find the notebook [cats-vs-dogs-redux.ipynb](https://github.com/masalha-alaa/dogs-vs-cats-pytorch/blob/master/cats-vs-dogs-redux.ipynb) in the root directory, in which you'll find a complete walkthrough of this work, or head over to my [Kaggle profile](https://www.kaggle.com/alaamasalha/cats-vs-dogs-redux) where you'll find the same notebook and see some of my other projects.

![image](https://user-images.githubusercontent.com/78589884/122687975-21a34000-d222-11eb-8fa3-ba18c0bf7756.png)
