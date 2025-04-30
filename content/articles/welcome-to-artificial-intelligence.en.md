---
title: "Welcome to Artificial Intelligence"
date: 2025-04-30T10:31:41+07:00
draft: false
---

# Introduction to Artificial Intelligence

| Natural Intelligence                         | Artificial Intelligence                                |
| -------------------------------------------- | ------------------------------------------------------ |
| the task is done by human using Intelligence | if we add this human natural intelligence to a machine |

Artificial Intelligence is
> The Science and Engineering of making Intelligent Machines
> ~ John McCarthy


# Road Map to Artificial Intelligence
![Road Map to AI](https://i.imgur.com/cqIX8Ea.png)
## 1. Programming Language
- Python
- R
- Lisp
- Prolog
- Java

## 2. Mathematical Knowledge
- Linear Algebra
- Probability and Distribution
- Statistics
- Vector Calculus
- Matrix Decomposition

## 3. Machine Learning Algorithm
> An algorithm is a step by step method of solving a problem

| Classification        | Algorithm                                                                                                                                               |     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Supervised Learning   | Decision Trees<br>Naive Bayes Classification<br>Ordinary Least Squares Regression<br>Logistic Regression<br>Support Vector Machines<br>Ensemble Methods |     |
| Unsupervised Learning | Clustering Algorithms<br>Principal Component Analysis<br>Singular Value Decomposition<br>Dijkstra's Algorithm                                           |     |

## 4. Machine Learning Tool
- Google's TensorFlow
- Torch
- Microsoft Cognitive Toolkit
- IBM Watson
- Amazon Web Services
- Accord.NET Framework
- Caffe
- Eclipse Deeplearning4j
- Apache Mahout
- Theano
- H20
- PredictionlO
- ai-one
- Protégé
- DiffBlue
- Nervana Neon
- OpenNN
- Veles
- Scikit-learn
## 5. AI Case Study
- Real Estate Price Prediction
- Image Recognition System
- Weather Prediction
- Self-Driving Car
- Automatic Music Composition
- Diagnosing of Medical Diseases
- Identifying the Fake News
- Books Recommendation

# Machine Learning

| Self Learning Algorithm                                                                                | Machine Learning                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Self Learning Algorithm is the algorithm which will learn by itself and takes own decision/predictions | Machine learning is a subset of Artificial Intelligence. Which works based on self learning algorithm using past experience or dayaset without being explicitly programmed. |

> Machine learning is the science of getting computers to act without being explicitly programmed 
> ~ Stanford

> Machine learning algorithms can figure out how to perform important tasks by generalizing from examples.
> ~ University of Washington

> Machine learning is based on algorithms that can learn from data without relying on rules-based programming.
> ~ McKinsey & Co.



| Supervised Learning                                                                                    | Unsupervised Learning                                                                                                                                                                      | Reinforcement Learning                                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| It infer a function from labeled data and use this function on new examples/never seen data/test data. | It is the training of an artificial intelligence algorithm using information that is neither classified nor labeled and allowing the algorithm to act on that information without guidance | It enables an agent to learn in an interactive environment by trial and error using feedback from its own actions and experiences |

## Supervised Learning
![Supervised Learning](https://i.imgur.com/ZyX38Ty.png)
### Supervised Learning Output

|            | Classification                                                                                                                                                                                                                     | Regression<br>                                                                                                                                                                                                          |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition | Classification algorithms are used when the desired output is a Discrete<br>label It is called as Binary Classification (Only two possible<br>outcomes)                                                                            | Regression algorithms are used when the desired output is a is a Real or Continuous value (Quantity)                                                                                                                    |
| Example    | 1. when filtering emails "spam" or "not spam"<br>2. when looking at transaction data, "fraudulent", or "authorized"                                                                                                                | 1. Predicting house price based on area<br>2. Predict the number of copies a music album will be sold next month                                                                                                        |
| Model      | - Logistic Regression<br>- Decision Tree<br>- Gradient-Boosted Tree<br>- Multilayer Perceptron<br>- One-vs-rest<br>- Naive Bayes<br>- Kernel Approximation<br>- K-Nearest Neighbors<br>- Support Vector Machine<br>- Random Forest | - Ordinary Least Squares Regression (OLSR)<br>- Linear Regression<br>- Stepwise Regression<br>- Multivariate Adaptive Regression Splines (MARS)<br>- Locally Estimated Scatterplot Smoothing (LOESS)<br>- Random Forest |


## Unsupervised Learning
![Unsupervised Learning](https://i.imgur.com/84QJK4O.png)
### Unsupervised Learning Output

|         | Clustering                                                                                                                           | Dimensionality Reduction                                                                                |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Example | - Recommender Systems<br>- Targeted Marketing<br>- Customer Segmentation<br>- Recommend products to customers based on Past purchase | - Big Data Visualization<br>- Meaningful Compression<br>- Structure Discovery<br>- Features Elicitation |

### List of UnSupervised Algorithms
- K- Means , K- Medoids Fuzzy C-Means
- Hierarchical
- Gaussian Mixture
- Neural Networks
- Hidden Markov Model

## Reinforcement Learning
![Reinforcement Learning](https://i.imgur.com/jeqhXPj.png)
### Types of Task

|            | Episodic Task<br>                                                                                                                                 | Continuous Task                                                                                                                                               |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition | It is having starting point and an ending point (a terminal state). This creates an episode - a list of States, Actions, Rewards, and New States. | This Task will continue forever (No terminal state). The agent has to learn how to choose the best actions and simultaneously interacts with the environment. |
| Example    | Super Mario<br>Begin : Episode begin at the launch<br>Ending : when you're killed or you're<br>reach the end of the level                         | Automated stock trading                                                                                                                                       |

### Types of Learning

| Monte Carlo Approach<br>                                                                                     | Temporal Difference Learning<br>                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Collecting the rewards at the end of the episode and then calculating the maximum expected future reward<br> | It will update its value estimation for the non-terminal states occurring at that experience.<br> |
| We start a new game with the added knowledge. The agent makes better decisions with each iteration           | It is also called TD(O) or one step TD                                                            |

### List of Reinforcement Learning Algorithms
- Monte Carlo
- Q-Learning
- Q-Learning with Normalized Advantage Functions NAF
- State-Action-Reward-State-Action (SARSA)
- Deep Q Network (DQN)
- Deep Deterministic Policy Gradient (DDPG)

---
Source:
https://www.udemy.com/share/101wLU3@RWdeqwDpmDHxFXMMhd30r8qN0hZUM7eIZoKyzh0flCJI9HDqI7JBptf0PY8U2J8t8A==/