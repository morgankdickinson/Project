# Artificial-Neural-Network
Our project was a convelutional neural network that took the CIFAR-10 dataset that contains over 60,000 images in 10 different catagories to train. 

## Overview
The first impotant part of a basic CNN is convolutional, activation, dropout, pooling. First we imported the necessary libraries and normalized the input data and created a seed to have reproductibility of the same image accuracy. This was done by dividing the image values by 255 and making the values into a float type. Since the images can't be accepted as is by the network, we use one-hot encode to turn the values into a bianry classification. One-hot encode removes an encoded variable and replaces it with an integer value. Next, we use the numpy command to_categorial() to use the one-hot encode. Our first layer of our sequential model will take the inputs and run the convelutional filters on them. We specify the number of filters as 32 and we use a 3x3 array as the size of our filter with the input shape. Padding = same to show that the image will not be changing in size and relu is the activation function that converts the nodes input into an output. The dropout layers are used to prevent overfitting and we used 0.2 to drop 20% of the existing connections. We also implemented batch normalization to input the heading into the next layer. As we go on, we adjust the filter size to 64 and 128 to allow the network to learn more complex representations. Max pooling is used to progressively reduce the spatial size of the representation to reduce the amount of parameters and computation in the network. After the convolutional layers are done processing we use flatten to gets a copy of the given array and flattens it into one dimention and then we pass it another dropout layer. The dense import is used to create the first densely connected layer. We specify the number of neurons as well as include the kernal constraint maxnorm to also prevent overfitting. In the final layer we use dense again with number of classes for the number of neurons and we used softmax activation function to select the neuron with the highest probability of the output, deciding that the image belongs to that class. We then specified 25 epochs to train for and used the adam optimizer because it is a stochastic gradient descent and performs well on harder problems.  Lastly, we chose our parameters, our seed value, and fit our model with a batch size of 100 that we trained on 50,000 samples and validated on 10,000 samples. It then prints the accuracy of the CNN.

## Results
Our CNN outputed an accuracy of 83.35% after running the CNN with 25 epochs and a batch_size of 54.

## Instructions on How to Run
To improve the accuracy of the CNN, a user could change and run a different number of epochs, a larger batch size if the user has a better proccessor, and a user can also change the pooling size by increments of 2 based on the image size that is being used. You can also change the size of the filters, though they should always be ascending, to a larger size to extract a higher number of abstractions from the raw pixel data that is fed into it.
