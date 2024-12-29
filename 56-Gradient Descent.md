**Gradient Descent**  An iterative optimization algorithm used to find a local minimum of a differentiable function  


**Types**
- Batch Gradient Descent
  -  Best for small datasets but can be slow and memory-intensive for large datasets.
  -  Works well on convex function which has a single minimum
- Stochastic Gradient Descent
  - Ideal for large datasets and online learning, but updates are noisy and may oscillate.
  - Works well on non-convex function also. reaches close to global minima comparatively faster but takes relatively long to conver after that
- Mini Gradient Descent
  - Combines the advantages of both BGD and SGD, providing a good balance between convergence speed and stability, and is often the most commonly used in practice for large datasets  
 
 ![Screenshot 2024-12-29 at 1 36 39 PM](https://github.com/user-attachments/assets/d85c07c5-8da3-4f28-bdce-5280b980c675)

