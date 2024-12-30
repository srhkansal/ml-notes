**Bias**
**Variance**

**Underfitting**
**Overfitting**
Performs well on training data but not so well in test data  

**Ridge Regression**
- ridge (L2)
  - Ridge regression is a technique that addresses overfitting & multicollinearity in linear regression
  - Loss = MSE + λ * (sum of squared coefficients) where λ (lambda) is the regularization parameter.
- Lasso (L1)
  - Feature selection is a primary objective.
  - when dealing with high-dimensional data
  - You believe that the true model involves only a small subset of the available features.
  - Loss = MSE + λ * (sum of absolute values of coefficients) 
- Elastic Net
  - Combines the penalties of both Ridge and Lasso
  - Loss = MSE + λ1 * (sum of absolute values of coefficients) + λ2 * (sum of squared coefficients) where λ1 and λ2 are the regularization parameters for L1 and L2 penalties, respectively.



![Screenshot 2024-12-30 at 3 38 20 PM](https://github.com/user-attachments/assets/7075ae46-ca71-4ade-a03d-e2d3e7923a86)
