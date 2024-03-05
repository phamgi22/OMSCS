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
### Why Lasso regression does variable selection but Ridge regression does not?
<img width="400" alt="Screenshot 2024-03-04 at 4 59 24 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/1512ca5d-88ee-4ad0-98d5-e1ca897b9752">

- Lasso regression:
  - |a1| + |a2| <= T
  - lasso regression solution must be inside the shaded diamond area
  - now we need to choose a solution that minimizes the sum of errors squared
  - possible error value can be graphed as an eclipse
  - as the total of error get larger, the error graph touches the shaded diamond
    - touch at corner --> one variable has been eliminated
    - if not touch corner --> more variables and smaller T value can cause eclipse to touch at corner --> more variable eliminated
- Ridge regression:
  - a1^2 + a2^2 <= T
  - ridge regression solution must be inside the shaded circle area
  - now we need to choose a solution that minimizes the sum of errors squared
  - possible error value can be graphed as an eclipse
  - two quadratic functions are very hard to touch at corner --> **cannotremove variables**
    
## The "bias-variance" tradeoff
- All patterns: real and random
- We can only fit more to all patterns or less to all patterns
  - capture both real and random
  - capture too little: underfit
  - capture too much: overfit
- A less fit model:  
  - use less variables
  - coefficients of variables are smaller
  - relationship between predictors and response is reduced (because prediction is closer to a0)
  - remove variable or minimize coefficients
    - create high **bias** in the model: make the model miss or minimize real effects (underfit)
    - **variance** also reduced: prediction closer to a0
- A more fit model:
  - use more variables
  - coefficients are larger
  - more differentiation between predictions due to large coefficients and amount of variables: high **variance**
  - more real effects are captured: low **bias**
  - more random effects also capture: overfit
    
- Validation help to pick model that find model that have high fit to real patterns
<img width="600" alt="Screenshot 2024-03-04 at 5 41 42 PM" src="https://github.com/phamgi22/OMSCS/assets/91588716/7a161905-a18a-4f11-90b9-d0ad41fed8b4">


- Experts can also help
## Ridge regression
- does not reduce the number of variables
- restricts regression coefficient magnitude
- if regression solution is outside of circle --> coefficients will be forced to be smaller according to T constraint
- if regression solution is inside of the circle --> coefficients wont be changed at all, unless T constraint get smaller than sum of coefficients squared (a1^2 + a2^2)
- decrease coefficient magnitude --> reduce **variance** in the model --> differences between model response decrease --> create more **bias**: capture less real effect --> but also capture less random effects --> reduce model fit
- this is a regularization approach that reduce the effect of variables on the model
- if T is too small then the model will be underfit


## Choosing a variable selectio model
- 

## Questions
1. Are forward selection, backward elimination and stepwise regression all greedy algorithm?   


