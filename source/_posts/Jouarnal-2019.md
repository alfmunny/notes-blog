
# 2019



## 2019-10 October


### 2019-10-24

Never use test data to do model selection. Generate validation set for it.
K-fold Cross-Validation is a cheap way to generate validation sets when the train data is scarce.
Get to know what is generalization error and training error. Overfitting, underfitting and model complexity. “Tunnable Parameters” -> “degree of freedom”. Deep.


### 2019-10-14

\#DLPyTorch4.1 - 4.3. Linear function of a linear function is itself always linear. So we need add some non linearity in to the hidden layer. That is the activation function, so we can’t merge two layers into one. And we get a multilayer perceptron!


### 2019-10-11

\#DLPyTorch3.5 - 3.7. Reread some softmax concepts. Maximum Likelihood Estimation is using product of all posibilities. Consider all events happen independently, what is the best the model that fits all the observations? Plug the observations into the model, calculate the whole prosibility of it, and maximize it. It’s basic. Is linear model always a fully conntected layer? Seems to be.


### 2019-10-10

\#DLPyTorch3.4 Softmax Regression for classification problems. Use the maximum likelihood estimation to get the loss function. As an intuition, softmax regression is like to add one more layer(softmax function) over the multiple linear regressions.

For n categories, we have n linear regressions. And then convert the n outputs to a distribution(Softmax).
To compare with the known distribution(calculated from labels), we use the Cross Entropy as the loss function. (Mean Square Error for linear regression)


### 2019-10-08

Deep learning is too deep. Should have done some serious programming and reading, end up in making this notes site to work, and write about 'About'. \`site.categories.findOne({name: "notes"}).posts\` saved the world.

