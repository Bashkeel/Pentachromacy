# Image Color Cluster Summarizer

### Goal of the Notebook:
The Color Cluster Summarizer will produce descriptive statistics about the **color spectrum of an image**. After loading an image, the summarizer will split the pixels into 5 distinct channels, based on their RGB colors.

The average color of each cluster will be reported via its **Common Color Name**, **Hex code**, **RGB value**, and **HSV value**.

The summarizer also reports the breakdown of colors within each cluster, based on the nearest **Common Color Name** from a pixel's RGB value

> ## [Skip to the Notebook](https://nbviewer.jupyter.org/github/Bashkeel/Pentachromacy/blob/master/A%20Pigment%20Of%20Your%20Imagination.ipynb)

### Steps Taken:
* Defining all functions used prior to beginning
* Loading the image using Python Imaging Library (PIL)
* Clustering the pixels into 5 groups using K-Means Clustering Algorithm
* Obtain the names of all the colors associated with the pixel clusters
* Find the average color in each cluster using the mean RGB value
* Create the image cluster partitions
    * Create the cluster masks 
    * Plot 5 replicates of the original image with the cluster masks
* Present the data in a tidy HTML table
    


### Issues:
> * HTML table does not load properly on Jupyter Notebook viewed through Github (To be fixed)
> * Images with less than 5 distinct colors will cause errors in K-Means Clustering


### The image used in this example:
![](Birdy%20Nam%20Nam.jpg)

### Image Cluster Partitions
Each pixel in the image is assigned to one of five groups based on the RGB value. These are called the **Cluster Partitions**. For each cluster partition, we turn hide the pixels of other partitions and reconstruct the image using only the pixel of the specific partition.

The border around each cluster partition represents the average color of the partition. This is calculated as the average RGB values of the partition.

![](Figures/Cluster%20Partitions.png)

### Cluster Breakdown
Next, we investigate the specifics of the cluster partitions. The cluster bar represents the proportion of pixels from the image that are in each cluster (**Pixels**)

In the table below, we report the average color of each cluster via its **Common Color Name**, **Hex code**, **RGB value**, and **HSV value**.

We also list the unique color name of each individual pixel in the partitions (**Tags**)

![](Figures/Cluster%20Bar.png)
![](Figures/Cluster%20Table.png)

<br>

### Required Libraries
* `Pillow`
* `numpy`
* `pandas`
* `scikit-learn`
* `colormaps`
* `webcolors`
* `Matplotlib`
* `IPython display`
