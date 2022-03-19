# neural_style_transfer

Here are two different implementation from two different purspective

The style transfer is inspired by the understanding of objects by a CNN. The earlier part of CNN can capture edges, curves etc but deeper layers of CNN can capture full object. Thus it is to say that earlier layers can capture style and later layers can capture content. Thus merging this two would give us an artistic style of images while keeping the main content. I have played around with CNN a bit and can be found [here.](https://github.com/hassanaliemon/understanding_and_visualizing_convolutional_networks) It would be much more convenient to have a understanding of CNN layers to have more insight and easy understanding about the style tranfer.

# First Approach
The first one is the implementation of this [paper](https://arxiv.org/abs/1508.06576)

In this implementation the model layers have been changed but during training time input image has been changed instead of model. The main theme is simple, adjust image parameters rather then model. Here, style transfer is achived by balancing two losses, style and content losses. Style and Content layers is added right after some selected layers and the output is then compared to get the loss. The main goal is to reduce both losses and change input image using these losses.

The implementation is mainly taken from [pytorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html)

# Second Approach

The second approach has taken the style transfer idea into next level. And the main [paper](https://arxiv.org/pdf/1603.08155.pdf) talks about more than style transfer. It can do some other tasks like image quality enhancement. 

The approach proposed in this paper is to train a model which takes an image and returns an image as well. The model changes the image using loss that vgg model produces. The model tries to reduce the Style and Content losses. 

The model takes an image and extracts its feature and reduces its size then it does the opposite. Residual blocks are used to capture features.

The implementation is taken from [here](https://github.com/jcjohnson/fast-neural-style)

The learning portion of mine is that, if we carfuly look at waht CNN or other layers caputre then we can use those captured feature to do something out of the box.

Another thing is to mention that, Document enhancement is possible using the same technique. Thus in future I would try to experiment about Document noise reudction and enhancement as well.

