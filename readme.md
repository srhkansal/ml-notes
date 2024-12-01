Datasets: titanic_dataset.csv
https://www.kaggle.com/datasets/heptapod/titanic?resource=download

Dataset: Restaurant Tips Dataset
https://www.kaggle.com/datasets/saurabhbadole/restaurant-tips-dataset

## Types of Machine Learning
Supervised Learning
    Classification Problem
        How many customer will leave platform
    Regression Problem
        How many customer will leave platform, so that we can give discount and
        Find chances for each customer so that we can plan appeasement discount
Un-supervised Learning

All Steps
0. Preprocess + EDA (Exploratory analysis) + Feature Selection
1. Extract Input and output columns
2. Scale the values
3. Train test split
4. Train the model
5. Evaluate the model | model selection
6. Deploy the model

Exploratory analysis
    Univariate analysis [single coulmn analysis] 
    Bivariate analysis [2 coulmns analysis]
    Multi-varaite analysis [Multi coulmns analysis]

Data types:
    Numerical data
    Categorical data


Step 1: [Frequently used dataframe functions to understand the dataset](https://github.com/srhkansal/ml-notes/blob/main/19-understand-your-data.md)  

Exploratory data analysis  
Step 1.1 | [Univariate data analysis](https://github.com/srhkansal/ml-notes/blob/main/20-eda-data-visualization.md)    
Step 1.2 | [Multivariate data analysis](https://github.com/srhkansal/ml-notes/blob/main/21-multivariate-analysis.md)   
Step 1.3 | [Pandas Profiling](https://github.com/srhkansal/ml-notes/blob/main/22-pandas-profiling.md)  

**Feature Engineering**
1. Feature Transformation  
2. Feature Connstruction  
3. Feature Selection  
4. Feature Extraction
        
**Feature Transformation**
    Missing Value Imputation
        Eliminate, Mean/Median, Most Frequent
    Handling Categorical Features
        Categorical to Numerical conversion | One Hot Encoding
        Numerical TO Categorical - Age 0-15 goes in a group
    Outlier Detection
    Feature Scaling
        [Standardization](https://github.com/srhkansal/ml-notes/blob/main/24-feature-scaling-standardization.md)

## Feature Connstruction
    In titanic dataset --> SibSp, Parch (parent child) can be converted to family column
## Feature Selection

## Feature Extraction
##############################################################

Feature Scaling --> Standardization (Z-score normalization) [Most problems will use Standardization]
                    (actual value - mean)/ standard deviation
                    Mean becomes zero and standard deviation becomes one 

                    When to use Standardization
                        K-means, KNN, PCA, ANN, Gradient Descent

                ---> Normalization  - Bring data to a column scale - Eliminate the units is an example
                    --->MinMaxScaling output in the range of [0 to 1] [When you know min and max]
                             = (x - x_min)/ (x_max - x_min)
                    --->Mean Normalization rarely used [-1 to 1]
                            = (x - x_mean) / (x_max - x_min)
                    --->Max absolute Scaling [rare, used for sparse data] 
                            = x/ absilute value of x_max
                    --->Robust Scaling [Used if data has many outliers]
                            = x - x_meadian/ IQR (x_75_percentile - x_25_percentile)


##############################################################
Encode categorical data 
                Nominal - When there is no ordering in values. Example - Male and Female
                            Use one hot encoder
                Ordinal - First Garde and Second Grade 

                ---> Ordinal Encoding [Ordinal categorical data]

                ---> Label Encoding [Nominal Categorical data] [Use Label Encoder]


    One hot encoder (Nominal categorical data)
                No of distinct values become column and you assign 1 or zeo to those column
                N categoris will become N column (reduce them to N-1 column by dropping 1st column)
                Multi coliniarity 
                May result in increased dimensionality 

##############################################################
Handle all columns in 1 go. SOme need scaling, some other need soemthing else lie imputers only
    Column Transfer:
                from sklearn.compose import ColumnTRansformer(transformer=[
                    ('tnsformerno1', SimpleImputer(),['fever']),
                    ('tnsformerno2', OrdinalEncoder(categoris=[['MIld','Strong']]),['cough']),
                    ('tnsformerno3', OneHOtEncoder(sparse=False, frop='first),['gender', 'city'])
                ], remainder = 'passthrough')
                transformer.transform(___)

##############################################################
Pipelines: Chains together multiple steps so that output of each step input to next | Day 29

##############################################################
    sns.displot tells you if data is normalization
    pd.skew is zero
    QQ plot tells you if data is normal 
    MathMatical Transformation (End goal to normally distribute the data)

    Function transformer #####
            Linear Regression, Logistic Regression need data to be normally distriburted
            Function transformer
            ---> Log Transoform 
                [Take log of value, right skewed data, not on negative values]
            ---> Reciprocal Transoform
                Small becomes big, big becomes small
            ---> Sq transform
                [left skewed data]
            ---> Square root transform
                Not much used
            ---> Custom transform

    Power transformer ##### [Used more than Functional transformer | any one can be used]
            Power Transoform
            ---> Box-Cox Transoform [Only Transoform is number for positive]
            ---> yeo - jhonson [Also applies to negative of zero] [default and used more]


##############################################################
Encode numerical data (convert to categorical data) []convert to contiguos intervals 
    Discritization or Binning
        Why?
            To better handle outliers
            Improve value spread

        Types
            Unsupervised Binning
                Equal width or uniform Binning
                Equal frequency or Quantile binning
                K means binning (intervals are called centroid)
            supervised Binning 
                Decision Tree Binning
            Custom Binning

    Binarization
        Convert contiguos values to binary

##############################################################
Handling mixed variables (Column has both Numerical and Categorical)
    Example: 
        Railway coach in Invaid- B5, C23, A12
        Split in 2 columns
            Cat  - Numerical
            B       5
            C       23
            A       12

        Column has data like - A, V, 1, 4, Z, 8
    
Date and Time Handling
    Example: 23 August 2024
    Has a lot of hidden information
        Day, Month, Yead, Day of week, weekend or not, quaerter?
    

    info() method gives date/time as object
    Convert this into datetime

##############################################################
Missing Values Handling  
    ---> Remove a rows [CCA - Complete case analysis][Not preffered] [remove rows where any column is missing]
            Only when Missing Completely at random [MCAR]
            if missing more than 5% - don't use this approach
            Think about removing the column of too many column values are missing
    ---> Impute them
            Univariate ######
                Numerical 
                    Mean [if distribution is normal] Or Median [if distribution is skewed][if missing value less than 5%]
                        May change distribute
                        Introduces outliers
                        Co-variance may change with other columns
                    Arbitrary [Mostly used with Categorical but can be done with numerical][Not used much]
                        Fill it with any arbitrary value [prefrred something which is not in your data]
                        variance
                        co-relation changes
                        When?
                            Data is not missing at random
                    End of distribution
                        Difficult to find arbitrary value.
                        Pick end of distribution value
                        if Normal distriburted
                            replace with Mean + 3 sigma
                            replace with  Mean - 3 Sigma
                        If Skewed distribution
                            Q3 - Q1

                        Variance
                            co-relation changes
                            When?
                                Data is not missing at random
                    Random [Both categorical and numerical]


                Categorical
                    Mod 
                        [Most Frequent][Missing Completely at random][Missing less than 5%]
                        May change data distribution
                    Missing
                        if more than 5% missing, create a new value for missing column values to "Missing"

                    Random Imputation
                        Random is picked from other column values randomly
                        Can be applied to any numerical and categorical columns
                        Not available in SKLearan
                        distribution is not affected, it largely remains same.
                        Does not work well for Decision tree based algorithm but good for Linear Regression
                        Memory heavy bacause you need data to pick random from on server
                        Variance also remains largely same
                        co-variance change is an issue
                        Extra handling: returned random val should be same for a given input variable
                    
                    Missing Indicator
                        Create a new column with value true and False
                        Age column has a new column Age_NA (if column has missing, Age_NA will have true)
                    
                    Automatically select value for Imputation
                        GridSearchCV (sklearn Automatically selects the right approach) [D37]

            MultiVariate ######
                    KNN imputer
                        Idea - you are like your neigbor
                        Replace with value which is closest to you
                        If K is 1 - ask one neigbor
                        If k is let say 3 - find 3 nearest neigbor, take average and replace missing values
                        Might need NAN Eucledian distance if neigbors have other missing values
                        More accuracy but time taking
                        Need training set on server bacause you would need all training data on server 
                        May need be good for large dataset due to above reason

                    Iterative imputer [also known as MICE - MultiVariate Imputation by Chained Equations]
                        Assumptions:
                            MCAR - you could not collect data for some rows
                            MAR - Few people did not fill the values ###### Use MICE  only here
                            Missing not at random - Data Eliminated intentionally 
                        
                        More accurate

                        Disadvantages:
                            Speed, Memory is an issue
                            
##############################################################
Outliner Detection and Removal
    Important to think if you need to remove them or handle them
    Logistic, Linear, Deep Learning are badly impacted due to outliers [if weights is a factor, outliers are mostly an issues]

    What to do with outliers:
    Trmmming - 
    Capping - 
        Put a limit on outliers
        anything beyound 100 Million in salary will be traeted as 100 Million
    
    Tecnhniques 
        Z-score [Only works for normal or near normal distribution]
        [mean + 3 sigma] or mean - [3 sigma is outliers]    
            if beyond this, consider them as outlier - do Trmmming or Capping

        IQR [Skewed data]
            Know box plot and IQR
            Q3 + 1.5 * IQR - Beyond this outliers
            Q1 - 1.5 * IQR - Beyond this outliers

        Percentile:
            Percentile capping is called winsorization

##################### Feature Extraction #####################
Principal Component Analysis (PCA)  [Supervised Machine Learning]
    Benefits:
        Higher to lower dimensions while still keeping the essence of data
        Faster algorithm
        Visualization as it reduces the dimensions
    
 















