**Feature Transformation**  
Modifying or changing the original features (variables) of a dataset to improve the performance of machine learning algorithms or to make the data more suitable for analysis.   

- Missing Value Imputation
  1. Eliminate, Mean/Median, Most Frequent
- Handling Categorical Features
  1. Categorical to Numerical conversion | One Hot Encoding
  2. Numerical TO Categorical - Age 0-15 goes in a group
- Outlier Detection
-  Scaling
   - Scaling adjusts the range of numeric features so they fit within a specific scale
   - Scaling required?
   - Mostly standardization is used. Normalization is used when you know min and max of feature value
   - Types
     - [Standardization](https://github.com/srhkansal/ml-notes/blob/main/24-feature-scaling-standardization.md)
     - [Normalization](https://github.com/srhkansal/ml-notes/blob/main/25-feature-scaling-normalization.md)
-  Encoding - Handling Categorical Features   
   - Ordinal Encoding - Applied on ordinal category data   
   - Label Encoding - Applied on output labels    
   - One hot endocing -  
     - Dummy variable trap - drop first variable(column) from newly generated columns  
     - OHE using most frequent variable - Replace less freuent values with others   
