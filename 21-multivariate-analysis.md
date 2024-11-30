**scatterplot (Numerical-Numerical)**  
import seaborn as sns  
sns.scatterplot(df['x'], df['y'],hue=df['z],style['a], size=['b])

**barplot (Numerical-categorical)**  
sns.barplot(df['category'], df['num'],hue=df['z],style['a], size=['b])

**boxplot (Numerical-categorical)**  
sns.barplot(df['category'], df['num'],hue=df['z],style['a], size=['b])

**distplot (Numerical-categorical)**  
sns.barplot(df['category'], df['num'],hue=df['z],style['a], size=['b])

**heatmap (categorical-categorical)**  
sns.heatmap(df['category'], df['category'])

**clustermap (categorical-categorical)**  
sns.heatmap(df['category'], df['category'])

**pairplot (categorical-categorical)**  
collection of scatterplots - multiple scatter plot is output

**scatterplot (Numerical-Numerical)**  
When x axis value is timeseries/ timebased
