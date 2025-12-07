# Math Analysis II Project
## Monte Carlo Estimation of Circle Area and Sphere Volume 
📘 **Project Overview**
This project implements Python programs that estimate:
- The area of a circle (2D)
- The volume of a sphere (3D)
- The volume of a hypersphere in higher dimensions
All calculations use the Monte Carlo simulation method, combined with visualization through Matplotlib.


🔹 **Estimating the Area of a Circle (2D)**
Setup
To begin, the program imports:
- NumPy for numerical computations
- Matplotlib for visualization
- SciPy for numerical integration

We define parameters such as:
- Circle radius
- Number of random samples N
- Dot size for plotting
- Boundaries of the square containing the circle

Method:
- Generate N random points inside a square of side length 2, centered at the origin.
- Calculate each point’s Euclidean distance from the center.
- Points with distance ≤ radius are counted as inside the circle.
- Estimate the area using the Monte Carlo formula:
Area≈(Points Inside/N)×(Square Side)<sup>2</sup>

 
To compare, SciPy performs double integration in polar coordinates to calculate the exact area.
Visualization
A custom Purple → Green colormap is used:
- Green = points inside the circle
- Purple = points outside
Simulations with 1,000, 10,000, and 1,000,000 trials show how accuracy increases with more samples.


🔹 **Estimating the Volume of a Sphere (3D)**

Method:
- The 3D version follows the same logic, with a few differences:
- Random points are generated in three dimensions.
- Distances are computed using a 3D NumPy array; squaring is applied element-wise.
- Using axis=1, we sum values across each point’s coordinates.

A 3D visualization is created using:
ax = fig.add_subplot(111, projection='3d')
This produces a clear model of how points fill the surrounding cube and sphere.


🔹 **Higher-Dimensional Sphere Volume**

The program also generalizes the Monte Carlo method to n dimensions:
- The user can input any number of dimensions.
- Points are generated in an n-dimensional hypercube.
- The fraction of points inside the hypersphere provides the volume estimate.

A dashed horizontal line is added using:
plt.axhline(e_area, color='blue', linestyle='--')
to mark the exact known value for comparison.


📎 **Summary**
This project demonstrates:
- Practical Monte Carlo simulation methods
- Visualization techniques in 2D and 3D
- Higher-dimensional geometry concepts
- Accuracy improvement with increased sample sizes
