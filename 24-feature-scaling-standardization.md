**Feature scaling**  
standardization   

![image](https://github.com/user-attachments/assets/2e2a800b-5e81-463d-ad99-4812948fa725)

New series -    
Mean is 0   
SD is 1   

​Mean centring    

**code**  
from sklearn.preprocessing import StandardScaler  
scaler = StandardScaler()  

**fit on the train**  
scaler.fit(X)

**transform trai and test both**  
x_scaled = scaler.transform(X)  

**Outliers effect**  
Outliers behave the same way even after standardization   

**When to use standardization scaling**  
K-means, KNN, PCA, ANN, Gradient Descent
