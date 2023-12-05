# Portfolio
This repository is a display of my personal portfolio. This README document include explanation and illustration of my **course design**, **personal interest projects** and some part of **internship program**. 

***

## Course Design
  ### ⭐ Implementation of bilateral filtering
Bilateral filtering is a type of nonlinear filtering that can achieve the effect of denoising and edge preservation. Compared to Gaussian filtering, bilateral filtering has an additional mask, which also considers grayscale similarity. Therefore, bilateral filtering is a compromise processing that combines the spatial proximity and pixel value similarity of the image. This course design replicates this processing.

#### 🚢Specific principles
The kernel of the filter is generated by **two functions**:
**Space distance**: refers to the Euclidean distance between a point in the neighborhood and the center point.
**Grayscale distance**: refers to the absolute value of the difference between the grayscale of a certain point in the neighborhood and the grayscale of the center point.

Compared to Gaussian filtering, bilateral filtering adds weights to grayscale information, meaning that within the neighborhood, points with grayscale values closer to the center point have greater weights, while points with larger grayscale differences have smaller weights. So the final weight size of the mask is determined jointly by the spatial domain Gaussian kernel function and the value domain Gaussian kernel function.
![principles of bilateral filtering](/image/bilateral filtering_image1.jpg "principles of bilateral filtering")
<p align="center"><img src="image/bilateral filtering_image1.jpg" width="650px"/>
Point p is the center of the mask (circled in yellow), and point q is a point in the neighborhood (circled in white). Two kernel functions are generated, one in the spatial domain and the other in the value domain, which are then multiplied to obtain the final kernel function. The input is convolved or correlated to obtain the output. From the graph, it can be seen that the edges are well preserved and noise is also suppressed.

#### 🚀Experimental results and conclusions

