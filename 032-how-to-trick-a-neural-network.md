### How to trick a neural network

_Julia Evans_

Step 0: Be very confused about neural network

Step 1: Read a cool paper: "Explaining and harnessing adversarial examples"

This paper said: sometimes neural networks work really well, but sometimes they totally fail.

Step 2: Spend 10 hours setting up neural network software.
Step 3: Download the neural network in the paper.
Step 4: Predict some things with it.
Step 5: Trick it
Step 4.5: Be very confused about neural network

To make the neural network thing it's more like something, take the derivative (ie backpropogation) and apply that to the image. Repeat until the network is very sure that the image is of the target.

Pandra to vulture took way more steps than velvet to paper towel.

This was all done with tensorflow.
