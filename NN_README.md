#**Neural Network module** 


###high level descrition and analysis

---

**general overview**

The module allows for a feed foreward neural network to be created using any arbitrary size and any number of layers. The methods are as follows:

* init(num neurons per layer) initializes the network to contain as many neurons as are specified by num neurons per layer, will attempt to read in from a file, or creates new weights if none were found
* Sigmoid(x, deriv): computes the sigasoid function or its derivative for any value of x
* dot with func(x, y, func): computes the dot product on x and y, applying the function func to every value in the new computed array
* get_output(data): computes the networks output for any given input data
* train(input data, output data): trains the network by teaching it to approximate the output data given the input data
* backpropigate(final error): backpropigates the error the the network given the final error of the final node(s)
* save data(): saves the networks weights into files in the current directory
* read data(): reads data previously saved by save data in the current directory


---

####lower level description of methods

**init**

arguments:

* num neurons per layer: an array of the number of neurons to have in each layer, for example: [5, 3, 2, 2] would mean a network with 5 inputs, connected to a hidden layer of 3 neurons, connected to a hidden layer of 2 neurons, connected to an output layer of 2 neurons

init is called when first constructing a neural network object. It will take in as parameters the number of neurons per layer. It automatically attempts to read in data stored by previous networks in the current directory. If the files are not found or there was some error in the files (wrong format, wrong size, file missing, etc) it will randomly initialize the weights. init will also initialize the layers to all be zero (layers is the output of each neuron, when nothing has been done, the neurons have not fired yet and thus layers is all zeros).

**sigmoid**

arguments:

* x: the value to compute the sigmoid value (or 