# SimpleImageRetrieval

Project Overview: Image Retrieval System Using HSV Color Histograms

This project involves building a simple content-based image retrieval system by leveraging color histograms in the HSV color space. Here's an overview of the methodology:

Color Histogram Computation
An image histogram represents the probability mass function of the image intensities. For color images, this concept is extended to capture the joint probabilities of the intensities across the three color channels (H, S, V). Formally, the color histogram is defined as: h{A,B,C}(a,b,c)=N×Prob(A=a,B=b,C=c), where A , B and C represent the three color channels (R, G, B or H, S, V) and N is the number of pixels in the image.
The color histogram is computed by discretizing the colors within an image and counting the number of pixels in each discrete bin. In this project, a custom function Cal256binHSV was implemented to compute a 256-bin HSV color histogram:
Hue (H): 16 bins
Saturation (S): 4 bins
Value (V): 4 bins

Image Database
A small database of four images was used for the project:
Elephant1.jpg
Elephant2.jpg
Horse1.jpg
Horse2.jpg

The 256-bin HSV color histograms for these images were computed using the Cal256binHSV function and plotted for visualization. Figure 1 displays the four histograms, each labeled with the corresponding image name.

Image Retrieval and Similarity Measurement
Each image in the database was used as a query to retrieve similar images from the database. The similarity between images was computed using histogram intersection, defined as: d(h,g)= min(∣h∣,∣g∣)∑A∑B∑C / min(h(A,B,C),g(A,B,C)), where |h| and |g| give the magnitude of each histogram, which is equal to the number of samples.

Results
For each query image:
The similarity scores between the query image and all database images were computed.
The database images were ranked based on the similarity scores.
Figures 2 through 5 display the retrieval results for each query image, showing:
Retrieved images in ranked order (Top match to fourth match).
Corresponding similarity scores for each match.


