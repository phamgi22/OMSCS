# Advance regression
## 1. Introduction to CART

### Purpose of this lesson?
- Learn how to use Tree to divide dataset and specify different models for each subset of the data

### Tree based method can be use in which contexts?
- Classification problems using CART(Classification and Regression Trees) approach
- Decision Making using the Decision Tree apprach

### Comparing Single Linear Regression and Tree Regression in **theory**
- Single Linear Regression model: fit the model using all the training data
- Regression Tree:
  - factors have differently in different combinations 
  - factor combintation example:
    - regression model for **25 and younger**: money spent = 50 + 13(number of children) + 0(income over 30k)
    - regression model for **older than 25** : money spent = 32 + 28(number of children) + 7(income over 30k)
    - factor "income over 30k": is only significant in one branch(older than 25)
  - regression tree model can split even more
    - example:
      - split **older than 25** into 2 branches: "26-50" and "50+"
      - split "26-50" into 2 branches: "no children" and "1+ children"
    - ending branch = leaf
  - depending on which branch the data point is defined: the specific tree regression model will be use for that data point
  - for some leaves: R squared will be lower than other leaves, we can investigate what other factors are more predictive for that leaf

### Trees Regression Model in practice
- Why we dont do full regression (with constant and coeficient of each variable like $y = a_0 + a_1x_1 + a_2x_2 + ... + a_nx_n$) ?
  - If we build a model for each node in the Tree, that is too many regression model with require too much computation
    - Note: even more computation with multiple regression trees 
  - There will be fewer and fewer data points at each node --> hard to avoid overfitting
- What should we do then?
  - Perform simple regression with only the constant y = $a_0$
  - $a_0 = average response in node = sum of all response in node / number of data points in node$

 <img width="1654" alt="Screenshot 2024-02-26 at 2 50 29 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/961f7357-cde8-4136-90dd-d275627ac85b">

 - Other places to use trees:
   - Logistic regression models:
     - Fraction of the node's data points with "true" response
     - Example: 2/4 = 50% of data points response enjoying the new cake with logistic regression model
   - Classification models
     - Most common classification among node's data points
   - Decision tree models:
     - Example: each leaf is the decision to "do i send a marketing email"
     - Going down the tree branches to see which decision to make
    
## 2. Branching
### This section purpose
- Learn how to specify a Tree
- Learn when to stop the Tree from branching
### How to branch?
- Need to answer these two questions:
  - Which factors should be in the branching decision?
  - How should we split the data?
- Common practice: branch on one factor as a time, but there are other ways of branching that can be considered
- Branching steps:
  - Use half of the data and build a regression model on it
  - When there is a leaf that we can branch on
    - Calculate the variance of the response among all data points in the leaf
    - Test splitting each factor to determine how much lower the total variance of the two branches would be compared to the least variance
    - Choose the factor with the lowest total variance
    - If the decrease in variance is more than threshold Delta and there are enough data points in each branch:
      - We make the split
      - Else, not enough benefit to branching and the leaf remained un-branched
    - When we finished branching, we use remaining half of the data (2nd half) to prune the Tree, steps are as follow:
      - For every pair of leaves created by the same branch, we use the 2nd half of the data to see if the estimation error is improved by the branch
      - If the branch improve error, the branches stay
      - If the branch make the error get larger or not change, the branches are removed
      - Final tree is finished
  - When a potential branch should be accepted/rejected?
    -  Rejected:
      - Low improvment benefit
      - One side of the branch has too few data points: each leaf contain at least 5% of the original data
  - Why we have to evaluate a potential branch?
    - We dont want to overfit the model
    - Overfitting our model can be costly ==> make sure each branch is greater than its cost
    - If branching so much that leaf node only have 1 data points, that data point is so specialize that the model at the leaf cant predict future data point

## 3. Random Forests (Many regression Trees)
### How Random Forests works in theory?
- Introduce randomness via bootstrapping
- Generate many different tree with different strengths and weaknesses
- The average quality of forest tree maybe better than a single tree with its specific strengths ans weaknesses
### How Random Rorests works in practice?
1. We give each tree a different set of data
- We have original data with n data points
- Tree 1,2,3 will also have a total of n data points
  - Some points appear mulitple times
  - Some points does not appear at all
2. Branching
- Randomly choose a small number of factors to make a subset
- Then choose an X number of factors in the subset for branching
- Common X value: 1 + log(n)
3. Dont need to prune the tree
- Trees has slightly different data
- We end up about 500-1000 Trees, each give a different model
4. Determine type of trees
- Regression Trees:
  - Use the average predicted response over all the trees in forest
- Classification Tree:
  - Use the "mode", the most common predicted response over all the trees in the forest
### Benefits of random forest approach?
- Tends to give better estimate overall because
  - While each tree might be overfitting in one place or another, each Tree overfit differently
  - Average between tree neutralize/flatten overfitting(overreaction to random effects)
### Drawback of random rorest approach?
- Much harder to explain/interpret the output of a random forest model
- Analytical software cant give us a specific regression or classification model from the data
### Note
- Random forest is also referred to as:
  - default model that can be tried if there is no strong reason to try something else
  - a good black box predictor that can be up and running quickly
  - not good for detailed insight into what is going on
## 4. Explainability/Interpretability
### What is explainability/interpretability?
- how easy or hard it is to understand how models create their output
- need to be able to explain how factors affect prediction to executive to convince them to use the model
- regression tree and random forest has low explainability
  - but has better prediction/result due to being able to identify more specific/complex patterns
- simple linear regression has high explainability 
  - but has less accurate prediction/results
- which model to choose depend on what it is used for
## 5. Logistic Regression
### Previously we learned:
- Regression models response is continuous
- Example: child height over the years
### Now we need to predict a probablitly that something will happen
- Linear regression will not work
- Probablity response will be between 0 and 1
- Example: probability that a person will pay their loan
- Logit model/logistic regression model will be best for this use case
  
<img width="600" alt="Screenshot 2024-02-26 at 5 44 43 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/5bab3c02-5a71-4605-95b7-7921115cb49d">

- if function output = negative infinity then p = 0
- if function output = positive infinity then p = 1
<img width="600" alt="Screenshot 2024-02-26 at 5 45 59 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/4b419a48-5296-46ea-a040-cc1af630a132">
- the value of coefficient of each variable can change how steep the curve is and where the steep part is
### Visualizing response of logistic regression curve
- How to visualize data points with same predictor value and same response?
  - enlarge dot to emphasize
    
  <img width="600" alt="Screenshot 2024-02-26 at 5 50 18 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/53b28b8f-efca-4c5f-903c-778dacc28253">
  
  - or alternatively, each bar is the percent(fraction) of the response that are 1 for each predictor value
  <img width="600" alt="Screenshot 2024-02-26 at 5 52 54 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/50cee39e-1374-467b-b37e-044f972899cb">

### Logistic regression vs Linear regression
- Similarities
  - Transformation of input data
  - Consider interaction terms
  - Variable selection
  - Logistic regression trees
  - Random logistic regression
- Differences
  - Logistic regression take longer to compute but still pretty fast
  - No closed form solution
  - Different way to understand model quality
### Measures of model quality
- Linear regression:
  - R squared value: estimate the fraction of the variance of the response that is explained by the model
- Logistic regression:
  - Pseudo R squared value: **Not** measuring fraction of variance like linear regression
### Logistic regression for Classification
- How? By thresholding, basically answer "yes" if probability p is at least some number, otherwise, answer "no"
- Example: if p >= 0.7 give loan, otherwise no loan
  
<img width="600" alt="Screenshot 2024-02-26 at 9 23 28 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/5f0c0776-1da3-402b-9e92-33fbdb317ef1">

About the graph:
- Use a Receiver operating characteristic curve or **ROC** where we plot sensitivy and 1 - specificity of the model for each threshold
- The Area Under the Curve is called **AUC**: show the probability that the model estimate a random "yes" point higher than a random "no" point
- Example:
  - Joe repaid the loan
  - Moe did not repay the loan
  - AUC = probability that the model give's Joe data point higher response value than Moe's
  - AUC = 0.5 -- meaning we are just guessing
  - AUC also called **concordance index**
### Why do we care about ROC and AUC
- Both ROC and AUC does **NOT** differentiate between the cost of False Negative and False Positive
- ROC and AUC give a quick estimate of the model quality
### How to determine which model give the highest value?
- Confusion matrix output
  
## 6. Confusion Matrices
### What do we learn in this section?
- Learn to measure how well a classification type model work
  - Can apply to classification models such as:
    - Support vector machine
    - K nearest neighbor
    - Logistic regression (Classification)
### What does confusion matrix show?
- Show how much the model is confusing the two categories
  
<img width="400" alt="Screenshot 2024-02-26 at 9 34 49 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/bf7f9728-d7a3-4370-9284-f98538b064fb">
- Example: 
  - True positive + False positive = total number of email in the inbox
  - Spam email = False positive / (True positive + False positive)
- **Sensitivity**: fraction of category member that are correctly identified
- **Specificity**: fraction of non-category member that are correctly identified

## 7. Situtationally-Driven Comparison
### What do we learn in this section?
- Learn to how to use measures of a model  quality to evaluate and compare different possibilities and choose the best one

### Example
- We built a SVM model to classify spam and real email
- 500 are real
- 500 are spam
  
<img width="400" alt="Screenshot 2024-02-26 at 9 58 03 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/ff61d7aa-b142-4f59-9b47-b356c19e068b">

- How to use this information to evaluate the svm model?
  - We need **cost of lost productivity**
  - Assume cost of lost productivity for the current classifying email case:
    - $0 for correct classification
    - $0.04 to read spam email
    - $1 to miss a real email
    - if 50% of email is spam: total cost = 490x0 + 10x1 + 100x0.04 + 400x0 = $14
      - overall cost per incoming email = 1.4cents/email
    - if 40% of email is spam: total cost = 490x(60/50)x0 + 10x(60/50)x1 + 100x(40/50)/0.04 + 400x(40/50)x0 = $15.2
      - overall cost per incoming email = 1.52cent/email
  - Lower overall cost per data point is better

### Advanced Topics in Regression
## What do we learn in this section?
- Advanced methods related to regression
  - Parametric methods: linear regression
  - non parametric methods: knn, spline regression
## Poisson regression
- Response of poisson regression model follow a Poisson distribution
  <img width="306" alt="Screenshot 2024-02-26 at 10 14 54 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/9659490a-472a-49c3-9f72-49840dab5cdd">
- Example: count arrivals at an airport security line
  - arrival is a function of time: $\lambda(x)$
- Parameter is a function of other attributes 
## Regression splines
- Function of polynomials that connect to each other
  - Connection point is knot
- Fit different functions to diffreent parts of the dataset
  - Smooth connections between knots
- Order k regression spline: the polynomial are all order k
- An implementation of regression splines is called Multi adaptive regression slines (MARS)
  - MARS is traded mark so MARS is called Earth in many statistical libaries

## Most advance: Bayesian regression
- Start with
  - Data
  - Estimate of how we think regression coefficients and the random error is distributed
-  Example: predict how tall a child will be as an adult, based on
  - Data: height of the child mother and father
  - Estimate coefficient from health expert suggest between 0.8 and 1.2
- Then use Bayes' theorem to update estimate based on the data we have
- most helpful when we dont have **not much data**
## Simple: KNN regression
- just plot all the data we have
- for new data that need to be predicted:
  - find the k closest data points to the new points
  - new data prediction = average the k data points response
- extra that we can do: weighting each dimension, remove dimension that not predictive
