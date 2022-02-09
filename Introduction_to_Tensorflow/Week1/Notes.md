# Introduction to Tensorflow for Machine Learning and Deep Learning
===================================================================
For applications where we cna figure out the rules to do something 
we should avoid using ML

We get a diagram of the form :-


Rules------------> 
					Traditional programming ----------> Answers
Data------------->

When we cant figrue out the rules but know what we want to happen
we would genereally use machine learning or deep learning techniques.

Answers------------> 
					Traditional programming ----------> Rules
Data------------->

Consider Activity recognition :-

if (speed < 4){                 or         if (speed == 0){
	status = Walking							status = ?;
	}else {									}else(speed > 0){
		status = Running						status = running,walking, sliding ? 
	}											}
	
While this holds ok  for the above case of activity recognition(walking or running) if we have an image 
related to golfing our methodology breaks completely.

Ulimately using machine learning we input our image and "classify" the action as golfing
beforehand and make our computer think of the calcuations which represent the 
image as a golfing rather than any other activity.

** If a problem can be represented by mathematical equations or numbers then it can be modelled as 
a machine learning problem.**

In activity recogntion we use the co-ordinates of the body to classify the activity.


# Hello World of Neural Networks
================================

X = -1 , 0 , 1 , 2 , 3 , 4
y = -3 , -1, 1 , 3 , 5 , 7

model = keras.Sequential([tf.keras.layers.Dense(units = 1,input_shape =[1])])

**Neural Networks**

These are set of functions that can efficintly learn patterns..
Simplest possible is the one which has only 1 neuron.

Dense -- to define a layer of connected neurons.

Since the successive layers are defined in a sequence so we use the "Sequential" method.
input_shape = [1] -- shape of the input laye
// for any model we need to enter an input_shape or have knowledge about the shape in which the model was build 

for example Unet architecture was build using 
572 x 572 (BGR) pixels images so unless we define the input shape our neural net will expect the images to be in the
same shape it was build on.

tf and keras do lots of math behind the scene in its predefined methods or functions

model.compile(optimizer = 'sgd',loss = 'mean_squared_error')

# How might a neural network work:-

Since the neural network has not seen the data or computed its related beforehand.
Neural network first makes a guess say relation between x and y is 10x - 8..
It then uses it already knows about to measure how good or bad its guess was
the loss function measures this and gives the o/p to the optimizer which then figures out
what to guess next and the expected result is that the loss would decrease in the next step till
the optimizer finds a good optimized solution or till we have called the number of epochs.

As this accuracy gets better and better and accuracy reaches close to a 100 then term convergence is used.

xs = np.array([-1 , 0 , 1 , 2 , 3 , 4],dtype = float)
ys = np.array([-3 , -1, 1 , 3 , 5 , 7],dtype = float)


mdoel.fit(xs,ys,epochs = 500) # training of the model is done on the fit method.

after training 

use predict to test your model

print(model.predict([10.0])) # our  answer would be almost 10.0 but not 10 correctly..

Neural network deal in probability.. very important 

Convergence
===========

An analysis that corresponds too closely or exactly to a particular set of data

