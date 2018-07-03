One vs. all
- leverages binary classification
- given a classification problem with N possible solutions, use one binary classifier for each possible outcome
- during training, the model runs through a sequence of binary classifiers, training each separately
- reasonable approach when number of classes is small, inefficient otherwise
- more efficient with a deep neural network with each output node representing a different class

Softmax (Full)
- assign decimal probabilities to each class in a multi-class problem
- implemented with a neural network just before the output layer

Candidate sampling
- Softmax calculates a probability for all the positive lables but only for a random sample of negative labels
- can improve efficiency when problem has many classes

One label vs. many labels
- Softmax assumes that each example is a member of exactly one class
- Softmax doesn't work when examples can be in multiple classes
- For multi-class membership, you must rely on multiple logistic regressions

