**Min-max scaling (this is the default and used 90% of the time)**    
After applyting min-max scaling distribution will be between [0, 1]  
Outliuers are impacted as we are pushing everything between [0,1]  

**Mean normalization [rarely used]**    
**MaxAb normalization**    
Used for sparse data. Not used much  

**Robust normalization**    
x_i = (x_i - x_median)/ IQR  
Robust to outliers. If there are many outliers  
