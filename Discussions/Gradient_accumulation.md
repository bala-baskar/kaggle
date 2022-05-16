When training a neural network, we usually divide our data in mini-batches and go through them one by one. The network predicts batch labels, which are used to compute the loss with respect to the actual targets. Next, we perform a backward pass to compute gradients and update model weights in the direction of those gradients.

Gradient accumulation modifies the last step of the training process. Instead of updating the network weights on every batch, we can save gradient values, proceed to the next batch and add up the new gradients. The weight update is then done only after several batches have been processed by the model.

Gradient accumulation helps to imitate a larger batch size. Imagine you want to use 32 images in one batch, but your hardware crashes once you go beyond 8. In that case, you can use batches of 8 images and update weights once every 4 batches. If you accumulate gradients from every batch in between, the results will be (almost) the same and you will be able to perform training on a less expensive machine!

[![gradient-accumulation.png](https://i.postimg.cc/mDwcjPn5/gradient-accumulation.png)](https://postimg.cc/ZBWKK548)

References:
1. [Gradient Accumulation](https://towardsdatascience.com/what-is-gradient-accumulation-in-deep-learning-ec034122cfa)
2. [Gradient Accumulation in PyTorch](https://colab.research.google.com/github/kozodoi/website/blob/master/_notebooks/2021-02-19-gradient-accumulation.ipynb#scrollTo=qquHcwRiEm58)