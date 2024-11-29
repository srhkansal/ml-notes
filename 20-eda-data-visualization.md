**Matplotlib**  
Matplotlib is one of the most popular and widely used Python libraries for creating static, animated, and interactive visualizations
Supports a variety of plot types, including line plots, bar charts, histograms, scatter plots, pie charts, 3D plots, and more
Integration with Other Libraries: Matplotlib integrates seamlessly with other Python libraries like NumPy, Pandas, and Seaborn

**Categorial data**  
  **sns**  
  sns module refers to Seaborn, a powerful Python data visualization library built on top of Matplotlib.  
  -- Countplot()   
     function in Seaborn is a specialized plot for visualizing the frequency distribution of categorical variables  
     Example - sns.countplot(x=None, y=None, data=None, hue=None, order=None, palette=None, **kwargs)  
  
  -- pie chart  
     df['some column'].value_counts().plot(kind="pie", autopct="%.2f")  

**Numerical data**  
 **Histogram** Make numerical data behave like categorical data - Create bins  
 import matplotlib.pyplot as plt  
 plt.hist(df['some column'], bins=50)  
 plt.dist(df['some column]) - Estimates the probability density function (PDF) of the data, smoothing the histogram.  
 plt.boxplot(df['some column])  
 ![image](https://github.com/user-attachments/assets/96c10f54-6f41-430a-a858-8387c69a2ec8)


 
