# Artificial Intelligence Lab 6 

Team:- Intelligent Machines
Members:- 
Riya Parikh (202051161)
Mugdha Sharma (20205214)
Janmay Joshi (202051210)
Foram Talpada (202051190)


# Hidden Markov Model

## What is Markov Process?
It is a mathematical model to describe a sequence of events in which the probability of future events depends only on the current state, and not on the sequence of events that preceded it.

## What is Hidden Markov Process?
It is a type of Markov process where underlying states are not directly observed, but are instead inferred from a set of observed outputs. The observed outputs are generated by the hidden states.
![HiddenMarkovProcess.png](https://github.com/foram-patel-0201/AI-Lab/blob/a21b841a02d9c4bd59609e8e0ec2b705330ebd35/HiddenMarkovProcess.png)

Parameters:-

T :- length of the observation sequence
N :- number of states in the model
M :- number of observation symbols
Q :- {q0,q1,...qN-1} = distinct states of Markov process
V :- { 0,1,...,M-1} = set of possible observations
O :- (O0,O1,....,OT-1) = observation sequence
A :- state transition probabilities
B :- observation probability matrix
π :- initial state distribution

## The three problems :-
1.  Given a known model what is the likelihood of sequence O happening?
    
2.  Given a known model and sequence O, what is the optimal hidden state sequence?
    
3.  Given sequence O and number of hidden states, what is the optimal model which maximizes the probability of O?
## Problem 1
Read through the reference carefully. Implement routines for learning the parameters of HMM given in section 7. In section 8, “ A not-so-simple example”, an interesting exercise is carried out. Perform a similar experiment on “War and Peace” by Leo Tolstoy.

[Solution Link](https://colab.research.google.com/drive/1C1Dvac5az9uIwqnqzA4wCwy9fvUEZKf-)
[Reference Link](https://www.cs.sjsu.edu/~stamp/RUA/HMM.pdf)



## Expectation Maximisation
The expectation-Maximization (EM) algorithm is iterative method for finding maximum likelihood estimates in cases where the observations are incomplete or missing. The algorithm consists of two steps:

1.  The expectation (E) step, where the expected value of the complete-data log likelihood is computed given the current estimate of the parameters
    
2.  The Maximization (M) step, where the parameters are updated based on the expected sufficient statistics from E step.
    

The algorithm is repeated until convergence, at which point the maximum likelihood estimates are obtained.


## Problem 2
Ten bent (biased) coins are placed in a box with unknown bias values. A coin is randomly picked from the box and tossed 100 times. A file containing results of five hundred such instances is presented in tabular form with indicating head and 0 indicating tail. Find out the unknown bias values.

[Solution Link](https://colab.research.google.com/drive/1aB4k6u-iquF5pnNVrBV-9o85hT4i9-g4?usp=sharing)
[Reference Link](https://www.academia.edu/2784600/What_is_the_expectation_maximization_algorithm)


-   The code implements the EM algorithm to estimate the unknown bias values of the coins.
    
-   The algorithm starts with an initial guess of the bias values and iteratively improves the estimates by calculating the expected number of heads and tails for each coin given the current estimates and updating the estimates based on these expected values.
    
-   The algorithm terminates when the improvement between two consecutive estimates is below a specified threshold.

## Problem 3

A point set with real values is given in dataset. Considering that there are two clusters, use EM to group together points belonging to the same cluster. Try and argue that K-means is an EM algorithm.

[Solution Link](https://colab.research.google.com/drive/1L-Tq8AFixNYS_2Rrnh_NOfQMv9lumG4L?usp=sharing)

-- Arguing that k-means is an EM algorithm

-   The basic idea behind k-means is to find the cluster centers that minimize the sum of squared distances from each data point to its assigned cluster center.
    

  

-   In the E-step, the data points are assigned to their nearest cluster center based on the Euclidean distance. In the M-step, the cluster centers are updated by computing the mean of all the data points assigned to that cluster. This process of E-step and M-step is repeated until convergence.
-    So, k-means can be considered as a simplified version of the EM algorithm where the distribution is assumed to be spherical Gaussian and the number of clusters is pre-defined. In EM, the distribution can be any kind of probability distribution, and the number of clusters can also be determined using different methods.
    

  

-   Thus, the k-means algorithm can be seen as a special case of the EM algorithm, and it is often referred to as the "hard EM" algorithm because it assigns each data point to a single cluster.
