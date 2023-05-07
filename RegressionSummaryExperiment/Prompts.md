I wanted to make Chat GPT (CGPT) 4 summarize 10 regression models in a tabular format with concrete examples. I wanted this to sort act like a quick refresher/cheat sheet for regression models. 

# Prompt 1 - Succeeded
After a few iterations, here's a prompt that gave me what I was looking for:

```
Give a tabular list of top 5 most commonly used regression models. Use one of the column to mention what analysis are they good for and one column to mention what analysis are they not good for. Use one column for a concrete example. In the example list which one is dependent variable and which one is an independent variable. 

Create a second table for each example. In this table use one column each to describe why a different regression method would be bad. Example row for the second table:

Col 1 : Predicting housing prices based on square footage (Dependent: Price, Independent: Square footage)
Col 2 : Simple linear regression is the right model
Col3 : It does not make sense to use Multiple linear regression as there is just a single independent variable.
Col4 : Logistic regression should not be used as the dependent variable is not a binary value
...
And so on.
Make sure to output 2 tables.
Make sure to use all examples from the first table in the second table.
Make sure to use all models from the first table as columns in the second table.
```

Table 1: Top 5 most commonly used regression models

| Regression Model | Good for | Not good for | Example (Dependent, Independent Variables) |
| --- | --- | --- | --- |
| Simple Linear Regression | Predicting a linear relationship between two continuous variables | Non-linear relationships or relationships between more than two variables | Predicting housing prices based on square footage (Dependent: Price, Independent: Square footage) |
| Multiple Linear Regression | Predicting a linear relationship between one continuous dependent variable and two or more independent variables | Non-linear relationships or relationships between more than two variables | Predicting employee salary based on education level and years of experience (Dependent: Salary, Independents: Education level, Years of experience) |
| Polynomial Regression | Predicting a non-linear relationship between one dependent variable and one independent variable | Relationships between more than two variables | Predicting stock prices based on time (Dependent: Price, Independent: Time) |
| Ridge Regression | Preventing overfitting and reducing the impact of multicollinearity in multiple linear regression | Predicting non-linear relationships or relationships between more than two variables | Predicting customer satisfaction based on demographic and transaction data (Dependent: Customer satisfaction, Independents: Age, Gender, Purchase amount, Frequency) |
| Logistic Regression | Predicting a binary outcome based on one or more independent variables | Predicting continuous outcomes or relationships between more than two variables | Predicting whether a customer will churn based on demographics and transaction data (Dependent: Churn, Independents: Age, Gender, Purchase amount, Frequency) |

Table 2: Examples of regression models for specific scenarios and why other models should not be used

| Example (Dependent, Independent Variables) | Simple Linear Regression | Multiple Linear Regression | Polynomial Regression | Ridge Regression | Logistic Regression |
| --- | --- | --- | --- | --- | --- |
| Predicting housing prices based on square footage (Dependent: Price, Independent: Square footage) | :heavy_check_mark: | :x: (there is just one independent variable) | :x: (relationship is linear) | :x: (relationship is linear) | :x: (dependent variable is not binary) |
| Predicting employee salary based on education level and years of experience (Dependent: Salary, Independents: Education level, Years of experience) | :x: (there are two independent variables) | :heavy_check_mark: | :x: (relationship is linear) | :x: (relationship is linear) | :x: (dependent variable is not binary) |
| Predicting stock prices based on time (Dependent: Price, Independent: Time) | :x: (relationship is non-linear) | :x: (there is only one independent variable) | :heavy_check_mark: | :x: (relationship is non-linear) | :x: (dependent variable is not binary) |
| Predicting customer satisfaction based on demographic and transaction data (Dependent: Customer satisfaction, Independents: Age, Gender, Purchase amount, Frequency) | :x: (not suitable for preventing overfitting or reducing multicollinearity) | :x: (not suitable for non-linear relationships) | :x: (not suitable for more than one independent variable) | :heavy_check_mark: | :x: (not suitable for continuous outcomes) |
| Predicting whether a customer will churn based on demographics and transaction data (Dependent: Churn, Independents: Age, Gender, Purchase amount, Frequency) | :x: (not suitable for binary outcomes) | :x: (not suitable for binary outcomes) | :x: (not suitable for more than one independent variable) | :x: (not suitable for non-linear relationships

NOTE: Not going to comment on how accurate the content is just yet - I will review it later.

I ran into a different problem though, described in the next section.

# Prompt 2 - Get output as HTML - Partial success

```
regenerate your previous output and format it as html. Put it inside a <div> element.
```

The html output I got has some html glitches (see file Prompt2.html):

- `<div>` element was not closed correctly.
- output is incomplete (second table element was not closed, data looks incomplete.)

It is still a decent output. I can write the remaining missing info by hand at this point if needed.

Experiment Date: May 7 2023
