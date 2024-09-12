# deep_learning_challenge

Data Preprocessing

What variable(s) are the target(s) for your model?
IS_SUCCESSFUL

What variable(s) are the features for your model?
APPLICATION_TYPE, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT, & STATUS

What variable(s) should be removed from the input data because they are neither targets nor features?
EIN & NAME

Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

number_input_features = X_train.shape[1]
hidden_nodes_layer1 =  5
hidden_nodes_layer2 = 3
hidden_nodes_layer3 = 2
nn.add(
    tf.keras.layers.Dense(units=hidden_nodes_layer1, input_dim=number_input_features, activation="tanh")
)

# Second hidden layer
nn.add(tf.keras.layers.Dense(units=hidden_nodes_layer2, activation="relu"))

# Third hidden layer
nn.add(tf.keras.layers.Dense(units=hidden_nodes_layer3, activation="relu"))


# Output layer
nn.add(tf.keras.layers.Dense(units=1, activation="sigmoid"))

This seemed like a good place to start and one run through the optimizer came to the result that the first activation layer should have been "tanh"

First run resulted in a model accuracy of 72.2%

Were you able to achieve the target model performance?
No

What steps did you take in your attempts to increase model performance?
Tried to optimize with a tuner, however the results failed consistently and did not allow me to find the best fit parameters to load into the model.  So, attempted to try manual optimization by changing the number of layers, the number of nodes, the number of epochs, and the activation.

Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
Overall results were after the manual optimization, I was only able to raise the percentage of accuracy by .3%.  I believe trying to convert the classifications to binary may help increase accuracy instead of Boolean.  I have the OneHotEncoder code bits sectioned out in my code, but I didn't activate them.  This would reduce some of the noise that the model is experiencing and could create a better result.


