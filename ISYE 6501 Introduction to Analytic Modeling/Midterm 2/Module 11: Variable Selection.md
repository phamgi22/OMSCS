## Introduction Variable Selection
### Why not want too many factors in the model?
- Two main reasons:
  - First:
    - when the number of factors is close to or larger the number of data point --> the model might fit too closely to the random effect
    - --> overfitting, model fit too closely to random effect
  - Second: simplicity, simple models are better than complex ones
    - Less data is required
    - Less chance of include insignificant factors
    - It's hard to explain a model with too many parameters --> Fewer factors model is easier to interpret to executive
    - **Example**: credit card applications cannot use factors that correlated to sex, marital status, disability: zipcode associate with race, 


## How to perform variable selection? We use models that are for variable selection
- Forward Selection approach:
  - Star with no factors
  - Find best new factor to add to the model
  - If new factor improves the model enough, we add the factor to the model
  - If there is no factor good enough to add, or we have added too many factors: stop
  - Optionally, go back and remove factors that are not good enough
    - "Good enough" can be determined however I want
    - Example:
      - factors that are good enough to add to the model for exploration are factors that have p <= 0.15
      - factors that need to be removed are factors that have p > 0.05
      - deductive from the above statement, final factors that are good enough to fit model at the end are factor with p <= 0.05
        
-  Backward Elimination:
  - Start with all factors
  - Continue to find the worst factor to remove from the model until:
    - there is no **bad enough** factor that can be removed
    - and the model does not have more factors than we want
    - **bad enough** determined by us just like **good enough**
   
- Stepwise regression: combination of forward and backward approach
  - start with all or no factors
  - at each step, remove or add a factor
  - remove right away any factors that no longer appear to be good
  - fit model with final set of factors
  - a stepwise selection method:
    - decision are made step by step
    - greedy algo
    - at each step take one thing that look bests **without** taking future options into consideration
    - stepwise selection methods are more **classical**
   
- **Metrics** used to pick a factor to add or remove:
  - p
  - r squared
  - AIC
  - BIC

- Other methods that are based on optimization models that make decisions more globally (looking at all options at the same time):
  - Lasso approach: add constraint to stand dard regression equation
    - reminder, we want coefficients of the model to minimize the sum of squared error 
    - and give regression equation(model) a budget T to use for coefficients
      - T budget will be distributed to the most important coefficients and the remaining coefficients will be 0, irrelevant
      - sum of coefficients can be too large (cant be greater than T)
    - must scale the data when we are constraining the sum of coefficients like this
    - how to pick the value of T, depend on:
      - number of variables
      - quality of the model
      - best tradeoff - use Lasso method
        
  - Elastic net method:
    - contrasting the combination of abs value of coefficients and their squares
    - must scale the data first
    - choose value T and lambda λ
 
- Ridge regression:
  - take out the abs value term from Elastic net
  - sometimes lead to better predictive model
  - **NOT A VARIABLE SELECTION METHOD**

## Lasso Regression vs Ridge Regression



## The "bias-variance" tradeoff
