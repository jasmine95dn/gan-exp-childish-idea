# gan-exp-childish-idea
**Note**: This is indeed a part of an exercise about GAN of the course I attended, the original source code is at [this link](https://github.com/eriklindernoren/Keras-GAN/blob/master/gan/gan.py)

The exercise focuses on experiments with the implemented GANs source code on the [CIFAR10](https://www.cs.toronto.edu/~kriz/cifar.html) dataset. What this exercise wants to see is how the performance of the source code changes when we change one line in it.

Here is a **List of (not so) childish ideas** and things I've tried out to get his code to run. Some of the ideas are sensible, while other ideas are not very useful. 
1. Replace line 99 `X_train = X_train.astype('float32') / 255.0` with `X_train = X_train / 127.5 - 1`.
2. Enlarge the number of “epochs” (actually iterations) from 30k to 100k.
3. Decrease the batch size.
4. Enlarge the number of neurons in each Dense layer.
5. Visualise the generated samples and print the loss less often.
6. Line 123: remove the 0.5 multiplication
7. Enlarge the latent dimension, see `self.latent_dim` (line 23).
8. Adjust the Adam learning rate (line 25).
9. Set in line 41 the discriminator trainability to True.
10. Remove the batch normalization lines (58, 61, 64).
11. Add Dropout
12. Change the `binary_crossentropy` loss to the L2 loss
13. Add more layers for a deeper network
14. Exchange the dence layers with convolutional ones.

**Task:** Classify the items from the list above, establishing whether implementing these ideas would

  a) Improve the quality of the generated samples. 

  b) Diminish the quality of the generated samples.

  c) Have a low impact where it is unclear if it would improve the quality of the generated samples or not.

Please consult [these ganhacks](https://github.com/soumith/ganhacks) for more general tips.

## Why 2 versions?
In the source code that I've received from my course, some hyperparameters have been changed. As I was so naive to run it without checking, I took the second run to see whether my naiveness influenced my experiments. Hmm...

## Future work
I'm considering to rerun the 2 again to see how would the history losses in both models and the accuracies might look like. Maybe I found out something more about this... 