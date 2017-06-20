# Intro to Machine Learning
<!-- toc -->
## Keywords
- statistical machine learning
- pigeon superstition
- no free lunch theorem
- inference
- okham's rasor / Lex Parsimoniae
- statistical machine learning
- reinforcement, unsupervise, supervised learning
- loss function
- overfitting
- bias-variance dilemma

## What is learning?
The first studies were made on animals. A mouse after eating something that got it sick, it will not eat it anymore.

Learning has to be integrated with _a priori knowledge_. 
The **no free lunch theorem** says that "no learning algorithm can work for all distributions"

The basic structure on which all learning algorithms are based is **inference**. Steps:
- guess the law
- compute del consequences (modeling)
- verify the agreement with experiments

We want to usse machine learning, because of the complexity of the problem and adaptivity of the computers

Okham's rasor: "Among competing hypotheses, the one with the fewest assumptions should be selected."

**Statistical machine learning** is the art of developing algorithm that allow computers to **learn** by constructing **models** of observing data through inference from sample with the intention  to use them for **predictions**

Types of learning:
- reinforcement learning: teaches the machine how to act in order to maximize a reward
    * data has partial target
    * markov processes
    * multi armed bandits
- unsupervised learning:
    * data has no target
    * density estimation
    * clustering
- supervised learning:
    * data has a target
    * regression (continuous labels)
    * classification (sparse labels)
    
The binary classification problem is modeled by a matrix that has rows for points and columns for features and a column vector of 1s and -1s.
So learning means finding a function $$f:X\to \{-1,1\}$$ in a space H that predictively approximates w

We assume that each example in the training set is independently and identically distributed.

n is the number of your points
d is the dimension your a living in
if $$n\lt\lt d$$ the space is so large that the samples become _sparse_ and therefore the model you build will not be significant

## How can I define the goodness of my model?
To assess a model we use a **loss function**

The real error your function is doing is called **expected risk**, which is the integral of the loss function over the whole plane.
Since you will never know all your points, but since you will never know every point this is just a theoretical measure

**empirical risk** is an unbiased estimate of the **expected risk**

**empirical risk minimization** is the method of trying all the possible functions and pick the one with le least empirical risk, therefor finding the best function for my training set

**training error** is a biased estimate, because it works perfectly only on the training set, but may not work on any other subset of data.
We phrase this as "minimizing the training error is prone to **overfitting**"

I can solve this problem adding an **inductive bias**, that is restricting **H** (the space where I look for my function)

This is called the **bias-variance dilemma**:
- bias: the loss of the main prediction relative to the optimal prediction (depends on H), it's basically the complexity of the function
- variance: the average loss of the predictions relative to the main prediction (depends on D)
- noise: the remaining loss that cannot be eliminated (unpredictable)

You can do nothing about noise, but you can balance bias and variance

The challenge of machine learning is finding this compromise.

## Examples of classifiers
Usually for classification problems you don't need to invent anything, you just have to tune an algorithm

- k-nearest neighbour
    * you pick the k (odd number) closer to the point and predict the label of the point will be the most frequent among the points
- linear discriminant analysis
    * tries to draw an ellipse around the points of the same class, such that they are as small and as far apart as possible
- support vector machine
    * the support vectors are the points of different classes that are closer together
    * then you draw the line that maximise the distance between the support vectors and the line
- decision tree
    * builds a tree of questions that allow you to find the class by travelling down the tree
- gaussian mixture
    * very similar to linear discriminant analysis
- artificial neural network
    * will talk about that later
    
### Iris dataset
Used as sample for all algorithms

50 samples from each of the 3 classes
4 features for each sample

## Model selection
Tuning parameters and choosing the best model. Main methods:
- k-fold cross validation: split the data into training and test data, so that we can test the model against unseen points
    * minimise the overfitting
    * dividing the data in n parts and always train on n-1 part, then test on the remaining one, do this n times
- bagging/boosting: randomly choose a subset of points many times (with or without reusing the same points)

## Feature importance
Not all the features have the same importance, therefore we may select the most important features, this is done through feature selection and ranking