# Portfolio
This repository is a display of my personal portfolio. This README document include explanation and illustration of my **course design**, **personal interest projects** and some part of **internship program**. 

***

## Course Design
  ### ⭐ Implementation of bilateral filtering
Bilateral filtering is a type of nonlinear filtering that can achieve the effect of denoising and edge preservation. Compared to Gaussian filtering, bilateral filtering has an additional mask, which also considers grayscale similarity. Therefore, bilateral filtering is a compromise processing that combines the spatial proximity and pixel value similarity of the image. This course design replicates this processing.

#### 🚢 Specific principles
The kernel of the filter is generated by **two functions**:
**Space distance**: refers to the Euclidean distance between a point in the neighborhood and the center point.
**Grayscale distance**: refers to the absolute value of the difference between the grayscale of a certain point in the neighborhood and the grayscale of the center point.

Compared to Gaussian filtering, bilateral filtering adds weights to grayscale information, meaning that within the neighborhood, points with grayscale values closer to the center point have greater weights, while points with larger grayscale differences have smaller weights. So the final weight size of the mask is determined jointly by the spatial domain Gaussian kernel function and the value domain Gaussian kernel function.

<p align="center"><img src="image/bilateral filtering_image1.jpg" width="650px"/>
  
Point p is the center of the mask (circled in yellow), and point q is a point in the neighborhood (circled in white). Two kernel functions are generated, one in the spatial domain and the other in the value domain, which are then multiplied to obtain the final kernel function. The input is convolved or correlated to obtain the output. From the graph, it can be seen that the edges are well preserved and noise is also suppressed.

#### 🚀Experimental results and conclusions

<p align="center"><img src="image/bilateral filtering_image2.jpg" width="650px"/>

The experimental results show that bilateral filters can effectively preserve image edge details while filtering out low-frequency noise components. For simple filtering, two sigma values can be set to the same value. If the value is less than 10, the impact on the filter is minimal. If the value is greater than 100, it will have a significant impact on the filter, making the image appear cartoonish.

### ⭐ Implementation of Simple Chat Software Based on TCP Protocol
#### 😎 Experimental Principles
Concurrent connection server oriented algorithms
Connection oriented servers achieve concurrency between multiple connections (not between requests).The main algorithms of the program are as follows:

    1. master thread：Create a socket and bind it to a well-known port of the provided service, keeping the socket connection oriented.
    2. master thread: Set the port to passive mode.
    3. master thread: Repeatedly calling accept to receive the next connection request from the client and creating a new slave thread or process to handle the response.
    4. slave thread: The connection request passed by the master thread begins.
    5. slave thread: Use this connection to interact with customers; Read request and send back response.
    6. slave thread: Close connection and exit.
    
The structure of Concurrent server process:
    1. The server includes a master process and zero or more slave processes. One thread per process.
    2. The main server uses accept to block calls, saving CPU resources. When a connection arrives, accept returns immediately.

#### ⚔️ Project Implementation Steps and Operations
    1. Compile program
    `$gcc -o chatclient chatclient.c  $gcc -o chatserver chatserver.c`


