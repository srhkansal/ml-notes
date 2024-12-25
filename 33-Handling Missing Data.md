**Handle missing data**

- remove (Complete case analysis) - remove data if data is missing in any coulmn
  - Used only when data is miussing at random and most data is available 
- Impute
  - Univariate
    - Numeric | Mean, Median, Random, End of distribution
    - Categorical | Mode, Missing
  - Multi-variate
    - KNN Imputer
    - Iterative Imputer (MICE) | Used only for Missing at random values

**missing values types**       
- Missing completely at random (MCAR)   
- Missing at random (MAR)  
- Missing not at random (MNAR)  
  
