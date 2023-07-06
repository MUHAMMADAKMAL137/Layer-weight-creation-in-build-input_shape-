# Layer-weight-creation-in-build-input_shape-
In the code you provided, a class called `Linear` is defined as a subclass of `keras.layers.Layer`. This class represents a linear layer in a neural network, with the equation `y = w.x + b`. Here's a breakdown of the code:

1. The `__init__` method is the constructor of the class. It initializes the object and sets the number of units (neurons) for the linear layer.

2. The `build` method is called when the layer is connected to an input for the first time. It is used to define the weights of the layer. Within this method, `self.w` and `self.b` are created as trainable weights using `self.add_weight`. The shape of `self.w` is `(input_shape-1, self.units)` where `input_shape` represents the number of input features. The shape of `self.b` is `(self.units,)`, matching the number of units specified.

3. The `call` method defines the forward pass of the layer. It takes the input `inputs`, performs matrix multiplication between the input and the weight matrix `self.w`, and adds the bias `self.b`. The result is returned as the output of the layer.

4. After the class definition, an instance of the `Linear` layer called `linear_layer` is created with `units=4`.

5. Finally, the code applies the `linear_layer` to a tensor of ones with shape `(2, 2)`. This is done by calling `linear_layer(tf.ones((2, 2)))`. The result is stored in `y`.

In summary, the code defines a custom linear layer that can be used as a building block in a neural network. It sets up the layer's weights in the `build` method and performs the forward pass computation in the `call` method. The instance of the `Linear` layer is then used to apply the layer to a tensor of ones, generating the output `y`.
