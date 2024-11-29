
1. **How big is data?**  
    df.shape()
    returns a tuple (number_of_rows, number_of_columns) | Example - (2223, 13)

3. **How does the data look like?**  
    df.head() -- gives top 5 rows  
    df.sample(5) -- random 5 rows

4. **What is the data type of columns?**  
    df.info() | provides a concise summary of the DataFrame  
        not-null count, data-type, memory space, numeric, vs categorical data  

5. **Missing values?**  
    df.isnull().sum()  
    displays missing values for each columns
    
6. **Insight into your data**  
    df.describe()  
    count, mean, std, min 25%, 50%, 75%, max

7. **Are there duplicate values?**  
    df.duplicated().sum()

8. **Check coorelation between columns**  
    df.corr()['column-name']  
    gives correlation between all columns. Answers between -1 to 1
