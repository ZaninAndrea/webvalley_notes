# Intro to Machine Learning
keywords:
- statistical machine learning
- pigeon superstition
- no free lunch theorem
- inference
- okham's rasor / Lex Parsimoniae
- statistical machine learning
- reinforcement, unsupervise, supervised learning
- loss function
- overfitting

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