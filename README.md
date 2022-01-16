# Max-Pooling-as-Non-linear-Activation
Inspired by a comment in a Computer Vision lecture offered by Michigan online (https://www.youtube.com/watch?v=ANyxBVxmdZ0&list=PL5-TkQAfAZFbzxjBHtzdVCWE0Zbhomg7r&index=7), 
that the max-pooling layer in CNN-based architectures can serve as non-linear activation, I have replaced the ReLu activation in a simple CNN-based classifier provided
in a Tensorflow Tutorial (https://www.tensorflow.org/tutorials/quickstart/advanced). 
The architecture is composed of a 2D Convolution layer with ReLu activation followed by a dense layer with ReLu activation, ending in a last dense layer outputting the
logits. The architecture is trained and tested on the MNIST dataset with five epochs. The results are as follows: 

  Epoch 1, Loss: 0.13081109523773193, Accuracy: 96.0633316040039, Test Loss: 0.0672094002366066, Test Accuracy: 97.90999603271484
  
  Epoch 2, Loss: 0.041160643100738525, Accuracy: 98.65666961669922, Test Loss: 0.062492676079273224, Test Accuracy: 98.0999984741211
  
  Epoch 3, Loss: 0.020556345582008362, Accuracy: 99.34666442871094, Test Loss: 0.059021007269620895, Test Accuracy: 98.25999450683594
  
  Epoch 4, Loss: 0.012619039043784142, Accuracy: 99.57333374023438, Test Loss: 0.06614897400140762, Test Accuracy: 98.22999572753906
  
  Epoch 5, Loss: 0.008782784454524517, Accuracy: 99.70832824707031, Test Loss: 0.06712484359741211, Test Accuracy: 98.37999725341797
  
  
I have replaced the Relu activation with a max-pooling layer. The full modified code can be found in the cnn.py file. The results are as follows:

  Epoch 1, Loss: 0.19458936154842377, Accuracy: 94.11000061035156, Test Loss: 0.11389774084091187, Test Accuracy: 96.2300033569336
  Epoch 2, Loss: 0.08985093235969543, Accuracy: 97.23833465576172, Test Loss: 0.09503132849931717, Test Accuracy: 97.15999603271484
  Epoch 3, Loss: 0.06469723582267761, Accuracy: 97.96666717529297, Test Loss: 0.10199881345033646, Test Accuracy: 96.91000366210938
  Epoch 4, Loss: 0.0470975860953331, Accuracy: 98.43333435058594, Test Loss: 0.10860186815261841, Test Accuracy: 97.0999984741211
  Epoch 5, Loss: 0.03559423238039017, Accuracy: 98.77832794189453, Test Loss: 0.109564408659935, Test Accuracy: 97.38999938964844
  
Findings:
While the final accuracy on the test set for the modified version (97.39) is comparable to the original result (98.37), we still see a drop in accuracy.
More importantly, we see that on the first epoch the accuracy on the test set of the modified version (94.1) is significantly lower than the original version (96.6),
which suggests that using max-pooling instead of ReLu slows down the the convergence rate to the optimum value. 
