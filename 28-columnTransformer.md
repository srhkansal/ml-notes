**ColumnTransformer example**
```
import numpy as np
import pandas as pd
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder, OrdinalEncoder
from sklearn.impute import SimpleImputer

# Example dataset with missing values
data = {
    'age': [25, 30, 35, np.nan],
    'income': [50000, 60000, 70000, 80000],  # Target variable, will pass through without transformation
    'gender': ['male', 'female', 'female', 'male'],
    'education': ['bachelor', 'master', 'phd', np.nan]
}

df = pd.DataFrame(data)

# Define feature columns
numeric_features = ['age']
categorical_features = ['gender']
ordinal_feature = ['education']
income_feature = ['income']

# Define transformers
numeric_transformer = [
    ('imputer', SimpleImputer(strategy='mean')),  # Handle missing numeric values by replacing with mean
    ('scaler', StandardScaler())  # Standardize the numeric features
]

categorical_transformer = [
    ('imputer', SimpleImputer(strategy='most_frequent')),  # Impute missing categorical values with most frequent value
    ('encoder', OneHotEncoder(drop='first'))  # One-hot encode categorical features, drop the first category
]

ordinal_transformer = [
    ('imputer', SimpleImputer(strategy='most_frequent')),  # Impute missing ordinal values with most frequent value
    ('encoder', OrdinalEncoder(categories=[['bachelor', 'master', 'phd']]))  # Ordinal encode the 'education' column
]

# Create the ColumnTransformer
preprocessor = ColumnTransformer(
    transformers=[
        ('num', numeric_transformer, numeric_features),  # Transform numeric features
        ('cat', categorical_transformer, categorical_features),  # Transform categorical features
        ('ord', ordinal_transformer, ordinal_feature),  # Transform ordinal features
        ('income', 'passthrough', income_feature)  # Pass through the 'income' column without transformation
    ])

# Fit and transform the data
X = df  # Input features (including the target column 'income' that will be passed through)
X_transformed = preprocessor.fit_transform(X)

print("Transformed features:\n", X_transformed)
```
