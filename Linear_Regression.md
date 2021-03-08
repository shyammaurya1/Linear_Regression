**Regression**-

Regression searches for `relationships` among variables.

For example, you can observe several employees of some company and try to understand how their salaries depend on the features, such as experience, level of education, role, city they work in, and so on.

This is a regression problem where data related to each employee represent one observation. The presumption is that the experience, education, role, and city are the independent features, while the salary depends on them.
***

The *dependent* features are called the `dependent variables`, outputs, or responses.

The *independent* features are called the `independent variables`, inputs, or predictors.

***
Regression problems usually have one continuous and unbounded dependent variable. The inputs, however, can be continuous, discrete, or even categorical data such as gender, nationality, brand, and so on.

It is a common practice to denote the outputs with 𝑦 and inputs with 𝑥. If there are two or more independent variables, they can be represented as the vector 𝐱 = (𝑥₁, …, 𝑥ᵣ), where 𝑟 is the number of inputs.
***

*When Do You Need Regression?*-

Typically, you need regression to answer whether and how some phenomenon influences the other or how several variables are related.

For example, you can use it to determine to what extent the experience or gender impact salaries.
***

**Linear Regression** - 

Linear regression is probably one of the most important and widely used regression techniques. It’s among the simplest regression methods. One of its main advantages is the ease of interpreting results.

*Problem Formulation* - 

When implementing linear regression of some dependent variable 𝑦 on the set of independent variables 𝐱 = (𝑥₁, …, 𝑥ᵣ), where 𝑟 is the number of predictors, you assume a linear relationship between 𝑦 and x.

>𝑦 = 𝛽₀ + 𝛽₁𝑥₁ + ⋯ + 𝛽ᵣ𝑥ᵣ + 𝜀. 

This equation is the `regression equation`. 

where
𝛽₀, 𝛽₁, …, 𝛽ᵣ are the regression coefficients, and 𝜀 is the random error.

>Linear regression calculates the estimators of the regression coefficients (predicted weights).

Thus,estimated `regression function`,
> 𝑓(𝐱) = 𝑏₀ + 𝑏₁𝑥₁ + ⋯ + 𝑏ᵣ𝑥ᵣ.

 This function should capture the dependencies between the inputs and output sufficiently well.


let 𝑦ᵢ be the actual response and 𝑓(𝐱ᵢ) be the predicted(estimated) response.


>The differences 𝑦ᵢ - 𝑓(𝐱ᵢ) for all observations 𝑖 = 1, …, 𝑛, are called the `residuals`. 

Regression is about determining the best predicted weights, that is the weights corresponding to the smallest residuals.

*To get the best weights, minimize the `sum of squared residuals (SSR)` for all observations*
 >𝑖 = 1, …, 𝑛: SSR = Σᵢ(𝑦ᵢ - 𝑓(𝐱ᵢ))².
 
  This approach is called the method of ordinary least squares.
***


*Regression Performance* -


The coefficient of determination, denoted as 𝑅², tells which amount of variation in 𝑦 can be explained by the dependence on 𝐱 using the particular regression model. 

Larger 𝑅² indicates a better fit and means that the model can better explain the variation of the output with different inputs.

The value 𝑅² = 1 corresponds to SSR = 0, that is to the `perfect fit` since the values of predicted and actual responses fit completely to each other.
***
**Types of Linear Regression** - 

1. `Simple linear Regression` = linear regression with a single independent variable, 𝐱 = 𝑥.

2. `Multiple Linear Regression` = linear regression with two or more independent variables.
3. `Polynomial Regression` =  linear regression in which, *polynomial dependence* between the output and inputs and, consequently, the polynomial estimated regression function.
***

1. **Linear Regression** -

![](https://files.realpython.com/media/fig-lin-reg.a506035b654a.png)

start with a given set of input-output (𝑥-𝑦) pairs (green circles). These pairs are your observations. 

*For example, the leftmost observation (green circle) has the input 𝑥 = 5 and the actual output (response) 𝑦 = 5. The next one has 𝑥 = 15 and 𝑦 = 20, and so on.*

*The estimated regression function (black line) has the equation 𝑓(𝑥) = 𝑏₀ + 𝑏₁𝑥.*

 >goal is to calculate the optimal values of the predicted weights 𝑏₀ and 𝑏₁ that minimize SSR and determine the estimated regression function.
 
  *The value of 𝑏₀, also called the intercept, shows the point where the estimated regression line crosses the 𝑦 axis. It is the value of the estimated response 𝑓(𝑥) for 𝑥 = 0. The value of 𝑏₁ determines the slope of the estimated regression line.*

The predicted responses (red squares) are the points on the regression line that correspond to the input values. 

*For example, for the input 𝑥 = 5, the predicted response is 𝑓(5) = 8.33 (represented with the leftmost red square).*

*The residuals (vertical dashed gray lines) can be calculated as*
> 𝑦ᵢ - 𝑓(𝐱ᵢ) = 𝑦ᵢ - 𝑏₀ - 𝑏₁𝑥ᵢ for 𝑖 = 1, …, 𝑛. 

They are the distances between the green circles and red squares. 

`When you implement linear regression, you are actually trying to minimize these distances and make the red squares as close to the predefined green circles as possible`

***
2. **Multiple Linear Regression** - 

If there are just two independent variables, the estimated regression function is 
>𝑓(𝑥₁, 𝑥₂) = 𝑏₀ + 𝑏₁𝑥₁ + 𝑏₂𝑥₂.

 It represents a regression plane in a three-dimensional space. The goal of regression is to determine the values of the weights 𝑏₀, 𝑏₁, and 𝑏₂ such that this plane is as close as possible to the actual responses and yield the minimal SSR.

The case of more than two independent variables is similar, but more general. The estimated regression function is
> 𝑓(𝑥₁, …, 𝑥ᵣ) = 𝑏₀ + 𝑏₁𝑥₁ + ⋯ +𝑏ᵣ𝑥ᵣ,

 and there are 𝑟 + 1 weights to be determined when the number of inputs is 𝑟.

***
3. **Polynomial Regression** - 

In addition to linear terms like 𝑏₁𝑥₁, your regression function 𝑓 can include non-linear terms such as 𝑏₂𝑥₁², 𝑏₃𝑥₁³, or even 𝑏₄𝑥₁𝑥₂, 𝑏₅𝑥₁²𝑥₂, and so on.

The simplest example of polynomial regression has a single independent variable, and the estimated regression function is a polynomial of `degree 2`.
> 𝑓(𝑥) = 𝑏₀ + 𝑏₁𝑥 + 𝑏₂𝑥².

Now,calculate 𝑏₀, 𝑏₁, and 𝑏₂, which minimize SSR. These are unknowns!

Keeping this in mind, compare the previous regression function with the function used for linear regression.
>𝑓(𝑥₁, 𝑥₂) = 𝑏₀ + 𝑏₁𝑥₁ + 𝑏₂𝑥₂
 
 They look very similar and are both linear functions of the unknowns 𝑏₀, 𝑏₁, and 𝑏₂.
This is why we can solve the polynomial regression problem as a linear problem with the term 𝑥² regarded as an input variable.

*In the case of two variables and the polynomial of degree 2, the regression function has this form.*

 >𝑓(𝑥₁, 𝑥₂) = 𝑏₀ + 𝑏₁𝑥₁ + 𝑏₂𝑥₂ + 𝑏₃𝑥₁² + 𝑏₄𝑥₁𝑥₂ + 𝑏₅𝑥₂². 
 
 The procedure for solving the problem is identical to the previous case. 
 
 apply linear regression for five inputs: 𝑥₁, 𝑥₂, 𝑥₁², 𝑥₁𝑥₂, and 𝑥₂². 
 What we get as the result of regression are the values of six weights which minimize SSR: 𝑏₀, 𝑏₁, 𝑏₂, 𝑏₃, 𝑏₄, and 𝑏₅.
***

**Underfitting** - 
underfitting occurs when a model can’t accurately capture the dependencies among data, usually as a consequence of its own simplicity. It often yields a `low 𝑅²` with known data and bad generalization capabilities when applied with new data.

**Overfitting** - 

Overfitting happens when a model learns both dependencies among data and random fluctuations. 

In other words, a model learns the existing data too well. 

Complex models, which have many features or terms, are often prone to overfitting. When applied to known data, such models usually yield `high 𝑅²`. However, they often don’t generalize well and have significantly `lower 𝑅²` when used with new data.

***
