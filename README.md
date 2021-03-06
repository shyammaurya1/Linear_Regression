# Linear_Regression
**Regression**-

Regression searches for `relationships` among variables.

For example, you can observe several employees of some company and try to understand how their salaries depend on the features, such as experience, level of education, role, city they work in, and so on.

This is a regression problem where data related to each employee represent one observation. The presumption is that the experience, education, role, and city are the independent features, while the salary depends on them.
***

The *dependent* features are called the `dependent variables`, outputs, or responses.

The *independent* features are called the `independent variables`, inputs, or predictors.

***
Regression problems usually have one continuous and unbounded dependent variable. The inputs, however, can be continuous, discrete, or even categorical data such as gender, nationality, brand, and so on.

It is a common practice to denote the outputs with π¦ and inputs with π₯. If there are two or more independent variables, they can be represented as the vector π± = (π₯β, β¦, π₯α΅£), where π is the number of inputs.
***

*When Do You Need Regression?*-

Typically, you need regression to answer whether and how some phenomenon influences the other or how several variables are related.

For example, you can use it to determine to what extent the experience or gender impact salaries.
***

**Linear Regression** - 

Linear regression is probably one of the most important and widely used regression techniques. Itβs among the simplest regression methods. One of its main advantages is the ease of interpreting results.

*Problem Formulation* - 

When implementing linear regression of some dependent variable π¦ on the set of independent variables π± = (π₯β, β¦, π₯α΅£), where π is the number of predictors, you assume a linear relationship between π¦ and x.

>π¦ = π½β + π½βπ₯β + β― + π½α΅£π₯α΅£ + π. 

This equation is the `regression equation`. 

where
π½β, π½β, β¦, π½α΅£ are the regression coefficients, and π is the random error.

>Linear regression calculates the estimators of the regression coefficients (predicted weights).

Thus,estimated `regression function`,
> π(π±) = πβ + πβπ₯β + β― + πα΅£π₯α΅£.

 This function should capture the dependencies between the inputs and output sufficiently well.


let π¦α΅’ be the actual response and π(π±α΅’) be the predicted(estimated) response.


>The differences π¦α΅’ - π(π±α΅’) for all observations π = 1, β¦, π, are called the `residuals`. 

Regression is about determining the best predicted weights, that is the weights corresponding to the smallest residuals.

*To get the best weights, minimize the `sum of squared residuals (SSR)` for all observations*
 >π = 1, β¦, π: SSR = Ξ£α΅’(π¦α΅’ - π(π±α΅’))Β².
 
  This approach is called the method of ordinary least squares.
***


*Regression Performance* -


The coefficient of determination, denoted as πΒ², tells which amount of variation in π¦ can be explained by the dependence on π± using the particular regression model. 

Larger πΒ² indicates a better fit and means that the model can better explain the variation of the output with different inputs.

The value πΒ² = 1 corresponds to SSR = 0, that is to the `perfect fit` since the values of predicted and actual responses fit completely to each other.
***
**Types of Linear Regression** - 

1. `Simple linear Regression` = linear regression with a single independent variable, π± = π₯.

2. `Multiple Linear Regression` = linear regression with two or more independent variables.
3. `Polynomial Regression` =  linear regression in which, *polynomial dependence* between the output and inputs and, consequently, the polynomial estimated regression function.
***

1. **Linear Regression** -

![](https://files.realpython.com/media/fig-lin-reg.a506035b654a.png)

start with a given set of input-output (π₯-π¦) pairs (green circles). These pairs are your observations. 

*For example, the leftmost observation (green circle) has the input π₯ = 5 and the actual output (response) π¦ = 5. The next one has π₯ = 15 and π¦ = 20, and so on.*

*The estimated regression function (black line) has the equation π(π₯) = πβ + πβπ₯.*

 >goal is to calculate the optimal values of the predicted weights πβ and πβ that minimize SSR and determine the estimated regression function.
 
  *The value of πβ, also called the intercept, shows the point where the estimated regression line crosses the π¦ axis. It is the value of the estimated response π(π₯) for π₯ = 0. The value of πβ determines the slope of the estimated regression line.*

The predicted responses (red squares) are the points on the regression line that correspond to the input values. 

*For example, for the input π₯ = 5, the predicted response is π(5) = 8.33 (represented with the leftmost red square).*

*The residuals (vertical dashed gray lines) can be calculated as*
> π¦α΅’ - π(π±α΅’) = π¦α΅’ - πβ - πβπ₯α΅’ for π = 1, β¦, π. 

They are the distances between the green circles and red squares. 

`When you implement linear regression, you are actually trying to minimize these distances and make the red squares as close to the predefined green circles as possible`

***
2. **Multiple Linear Regression** - 

If there are just two independent variables, the estimated regression function is 
>π(π₯β, π₯β) = πβ + πβπ₯β + πβπ₯β.

 It represents a regression plane in a three-dimensional space. The goal of regression is to determine the values of the weights πβ, πβ, and πβ such that this plane is as close as possible to the actual responses and yield the minimal SSR.

The case of more than two independent variables is similar, but more general. The estimated regression function is
> π(π₯β, β¦, π₯α΅£) = πβ + πβπ₯β + β― +πα΅£π₯α΅£,

 and there are π + 1 weights to be determined when the number of inputs is π.

***
3. **Polynomial Regression** - 

In addition to linear terms like πβπ₯β, your regression function π can include non-linear terms such as πβπ₯βΒ², πβπ₯βΒ³, or even πβπ₯βπ₯β, πβπ₯βΒ²π₯β, and so on.

The simplest example of polynomial regression has a single independent variable, and the estimated regression function is a polynomial of `degree 2`.
> π(π₯) = πβ + πβπ₯ + πβπ₯Β².

Now,calculate πβ, πβ, and πβ, which minimize SSR. These are unknowns!

Keeping this in mind, compare the previous regression function with the function used for linear regression.
>π(π₯β, π₯β) = πβ + πβπ₯β + πβπ₯β
 
 They look very similar and are both linear functions of the unknowns πβ, πβ, and πβ.
This is why we can solve the polynomial regression problem as a linear problem with the term π₯Β² regarded as an input variable.

*In the case of two variables and the polynomial of degree 2, the regression function has this form.*

 >π(π₯β, π₯β) = πβ + πβπ₯β + πβπ₯β + πβπ₯βΒ² + πβπ₯βπ₯β + πβπ₯βΒ². 
 
 The procedure for solving the problem is identical to the previous case. 
 
 apply linear regression for five inputs: π₯β, π₯β, π₯βΒ², π₯βπ₯β, and π₯βΒ². 
 What we get as the result of regression are the values of six weights which minimize SSR: πβ, πβ, πβ, πβ, πβ, and πβ.
***

**Underfitting** - 
underfitting occurs when a model canβt accurately capture the dependencies among data, usually as a consequence of its own simplicity. It often yields a `low πΒ²` with known data and bad generalization capabilities when applied with new data.

**Overfitting** - 

Overfitting happens when a model learns both dependencies among data and random fluctuations. 

In other words, a model learns the existing data too well. 

Complex models, which have many features or terms, are often prone to overfitting. When applied to known data, such models usually yield `high πΒ²`. However, they often donβt generalize well and have significantly `lower πΒ²` when used with new data.

***
