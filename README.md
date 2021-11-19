# Image-Search-Engine
An image search engine made using python GUI, that extracts and stores features from images in database in the form of color correlogram and compares each against that of the query image, to retrieve similar images from the database.

## What are Image Search Engines?
Image search engines that quantify the contents of an image are called Content-Based Image Retrieval (CBIR) systems. The term CBIR is commonly used in the academic literature, but in reality, it’s simply a fancier way of saying “image search engine”, with the added poignancy that the search engine is relying strictly on the contents of the image and not any textual annotations associated with the image.

## Motivation:
As we all know, searching for images using “names” and “tags” is highly inefficient. Using language and keywords to describe something that is fundamentally visual is a tremendous hassle, whether you're labelling and categorising your personal photos, looking for stock pictures for your corporate website, or simply attempting to locate the appropriate image for a blog post. Hence, here I will be attempting to make everything easier by creating an image search engine in python (OpenCV).

## Steps to follow:
* Defining our image descriptor
* Indexing your dataset
* Defining your similarity metric
* Searching

## Flow Chart:
_Oversimplication of how the image search engine works._

![Data Flow](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Data_Flow.png)

![Processes](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Processes.png)

## Tools and libraries used:
_**1. OpenCV**_
_**2. Numpy**_
_**3. Imutils**_
_**4. Glob**_
_**5. Argparse**_

## Algorithm
The query image will be segmented into 5 parts as shown below. Each part will define various features of the image. Each of the parts will be extracted for features, after the image is converted to HSV format from RGB format. Although, RGB format images is easier to process than HSV images, the HSV images appeal more to human vision, when it comes to perceiving those images to the fullest. Hence, after the conversion, the parts will be extracted for the features, to form a color correlogram. The color correlogram will be made up on the basis of the probability of the pixel colors, and how many times a particular shade of color appears in each region, in the form of pixels.

![Query Image Segmented](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/temp.png)

## How to perform the execution?
Download this repo and change the directory to the main folder containing all the files in this repo, through the command prompt, and type the following commands.

```
py index.py --dataset ..\images\ --index ..\index\index.csv

py search.py --index\index.csv --query ..\query\qimg1.png --result-path ..\images\
```

## Outputs after execution:

![Query Image](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Query_Image.png)

![result Images](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Result_Images.png)

## GUI (Graphical User Interface):

![GUI Bar](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Bar.jpg)

![GUI Display](https://github.com/astrodestroyergithub/Image-Search-Engine/blob/master/assets/Display.jpg)

## References

[1] **Virage image search engine: an open framework for image management** Jeffrey R. Bach, Charles Fuller, Amarnath Gupta, Arun Hampapur, Bradley Horowitz, Rich Humphrey,  
Ramesh C. Jain, Chiao-Fe Shu 


[2] **Query by Image : The QBIC System** Myron Flickner, Harpreet Sawhney, Wayne Niblack, Jonathan Ashley, Qian Huang, Byron Dom, Monika Gorkani, Jim Hafher, Denis Lee, Dragutin Petkovie, David Steele, and Peter Yanke

[3] https://www.pyimagesearch.com/2014/12/01/complete-guide-building-image-search-engine-python-opencv/