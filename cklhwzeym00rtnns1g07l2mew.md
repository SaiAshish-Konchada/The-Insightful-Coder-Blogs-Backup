## Basic Programs on Computer Vision

What's up, everyone?🙌🏻 Welcome to the  [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)  🧠 

I'm  [Sai Ashish](https://www.linkedin.com/in/sai-ashish/) and today we are going to explore some fundamental programs of image processing and computer vision which we require as a prerequisite for any Computer Vision applications such as Face Detection or Face Recognition👦🏻

If you're new to the world of Computer Vision, I suggest you check out [The Easiest Guide to Get You Started on Computer Vision](https://theinsightfulcoder.com/the-easiest-guide-to-get-you-started-on-computer-vision) as we will be requiring it for the builds in this article 👁 

Without further ado, let's dive in🚀 

In This Article, We Are Going to Explore:

```
1. the Imutils Library
2. How to Resize an Image Using Imutils?
3. How to Convert a Colorful Image Into Grayscale?
4. How to Apply Gaussian Blur to an Image?
5. How to Apply Threshold to an Image?
```

## What Is Imutils?

[Imutils](https://pypi.org/project/imutils/) is a series of functions to implement basic image processing functions such as translation, rotation, resizing, displaying Matplotlib images, detecting edges, and much more easier with OpenCV.

To install imutils, you should already have  NumPy, SciPy, Matplotlib, and OpenCV  installed. To install these modules into your python environment, run the following commands in the terminal.
```
pip install numpy
pip install scipy
pip install matplotlib
pip install opencv-python
```
And then execute, 
```
pip install imutils
```
## Program 1: Resizing an Image:

![Illustration of Resizing an Image](https://cdn.hashnode.com/res/hashnode/image/upload/v1614075742736/Oa1mnRWWz.png)

### Why Do We Resize an Image for Computer Vision?

Machine learning models train on 1000s of images and larger the size of the images, more is the time taken for the training. Resizing helps in reducing the size of the image. Plus, it might occur the images we use to train the model may be of different sizes which is not feasible for deep learning models either. Resizing maintains a constant size and hence is a very important part of preprocessing an image in computer vision.

### How to Resize an Image Using Imutils?

To resize an image, we use the imutils.resize() function. 

**Syntax:**

imutils.resize(image,width=newwidth)

**Parameters:**

**image:** the loaded image<br>
**width:** the new width you want to specify

**Example:**

```
# resizing an image
imutils.resize(image, width=500)
```
### Let's see resizing in action 🔥

![Source Code for Resizing an image using Imutils module of Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1611857923559/W43UM0tOP.png)

You can directly download the source code and the image for resizing from  [here](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Resizing%20Image%20using%20Imutils.py).
 
## Program 2: Converting an Image Into Grayscale

![Illustration of Converting an Image into Grayscale](https://cdn.hashnode.com/res/hashnode/image/upload/v1614075943185/lb5Daic7r.png)

### What Is Grayscaling?

Grayscaling is the process of converting an image from other color spaces to shades of gray.

### Why Do We Convert Images Into Grayscale?

Apart from giving your pictures a retro filter, Grayscale has a greater application in Computer Vision. They are:

**Dimension Reduction:** Color images are formed by the shades of 3 primary colors-Red, Green and Blue whereas a grayscale image is formed used only one color- grey. When you convert a colorful image to grayscale, the dimension of an image is reduced drastically, from 3 → 1.

**Reduces model complexity:** In Deep Learning (the subset of Machine Learning), you'll encounter something known as Neural Networks. These Neural networks have to be trained using 1000s of images. When you use color images, you'll have to feed the Neural network the Red frame, the Green frame and the Blue frame for each of the 1000 images. This will increase the time required to train the model and the complexity as well. By using Grayscale, you just have to feed one single frame, the gray one. Therefore, the complexity is reduced by three times.

**Algorithms Requirements:** Some of the algorithms built for Computer Vision under the OpenCV library work only on Grayscale images.  

### How to Convert a Colorful Image Into Grayscale?

As I said earlier, you require only a single line of code to convert a colorful image into Grayscale. And that one line of code is :

```
#converting color image into Grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 
```

OpenCV provides a powerful function called cvtColor which automatically converts our colourful image from one format to other. There are over 150 color space conversions to chose from. For example, to convert an image from HSV to Grayscale, we'd use HSV2GRAY instead of BGR2GRAY.

**Syntax:**
 
cv2.cvtColor(src, code[, dst[, dstCn]])

**Parameters:**

**src:** the image whose color space is to be changed <br>
**code:**  name of the color space conversion code, eg. BGR2GRAY <br>
**dst:** optional parameter indicating output image of same size and depth as src image<br> 
**dstCn:** optional parameter indicating the number of channels in the destination image. If 0 then the number of the channels is derived automatically from src and code<br> 

**Note:** BGR is the same as RGB except the order of areas is reversed. Red occupies the least significant area, Green the second (still), and Blue the third. To know more about the difference between RGB & BGR, visit  [here](https://stackoverflow.com/questions/367449/what-exactly-is-bgr-color-space). 

**Example:**

```
#Saving the grayscale image
cv2.imwrite("Grayscale Image", gray_image)
```
### Let's see the code in action 💪🏻

![Source code of Converting an Image into Grayscale using python](https://cdn.hashnode.com/res/hashnode/image/upload/v1611755537491/GsgO_NgYX.png)

You can directly download the source code and image to convert a colorful image into grayscale from  [here](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Color%20Image%20to%20Grayscale%20Image.py).

The Flow Summary:

1. Load the image using imread()
2. Convert into grayscale using cvtColor(image, cv2.COLOR_BGR2GRAY)
3. Display image using imshow()
4. Save image using imwrite()

## Program 3: Converting an Image Into Gaussian Blur

![Illustration of Converting an Image into Gaussian Blur using Python OpenCV](https://cdn.hashnode.com/res/hashnode/image/upload/v1614076241576/C53GeqHzl.png)

### What Is Gaussian Blur?

Gaussian Blur is an operation commonly used to blur images using a filter.

### Why Do We Convert Images to Gaussian Blur?

Gaussian Blur, or simple blurring an image provides great benefits, such as:

**1. Noise Removal:** Image noise is random variation of brightness or color information. By applying blur, we restrict the high intensities and allow only the low intensities and hence noise is removed.

**2. Smoothening:** Blurring helps in the smoothening of image, that is to remove any distortions and unevenness in the image.

**3. Concealing identity: ** We can conceal/hide the details which we do not want to appear in our image.

### How to Convert an Image to Gaussian Blur?

Similar to converting an image to Grayscale, we have a one liner code, a useful function which does our job for us. The name of the function is GaussianBlur() function.

**Syntax:**

GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType=BORDER_DEFAULT]]])

**Parameters:**

**src** − the source or input image <br>
**dst** − the destination or the output image <br> 
**ksize** − object representing the size of the kernel. It is always a positive odd number. More the size, more is the blur.

Let's say you've a photograph in your hand. If you want to blur it, you apply pieces of wax(butter) or parchment paper over it. You can imagine this translucent piece of paper as the kernel. However, digitally, things are done a little differently. In a digital image, we use a matrix and multiply it with the intensity of the pixels of the image to achieve blurring, sharpening etc.

**sigmaX** − A variable representing the Gaussian kernel standard deviation in X direction<br>
**sigmaY** − A variable representing the Gaussian kernel standard deviation in Y direction

When you apply a wax paper, the wax paper is translucent equally throughout. Similarly, we have to maintain the values of the kernel around a certain point(the average). sigmaX defines the variation between the average and other value of the pixels in an image. If 0 is given, sigmaX and sigmaY are calculated from the kernel of the image. If sigmaX is given, sigmaY is equal to sigmaX.

**borderType** - specifies type of border the boundary of image should have

**Example:**
```
gaussianBlurImg = cv2.GaussianBlur(image, (21, 21), 0)
```
### Let's Apply Some Blur 🖼:

![Source code of Converting an Image into Gaussian Blur](https://cdn.hashnode.com/res/hashnode/image/upload/v1611752178823/jNywI8AHB.png)

From above, you can see that I chose the source as the loaded image, ksize as (21,21) and sigmaX is given 0.

You can directly download the source code & image to apply gaussian blur from  [here](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Gaussian%20Blur.py).

## Program 4: Applying Threshold to an Image

![Illustration of Applying threshold to an image using Python OpenCV](https://cdn.hashnode.com/res/hashnode/image/upload/v1614076372390/rXtGDFILA.png)

### What Is Thresholding an Image?

Thresholding is the simplest way to apply segmentation to an image. 

### What Is Segmentation in Image Processing?

It is the process of separating segments of an image from one another, in simple terms to differentiate and separate the light and the dark regions of an image. 

### Why Do We Apply Thresholding?

Thresholding is very useful to separate, analyse and extract features from an image. 
It basically isolates the relevant information from the other.

### Concept of Threshold:

The concept of thresholding is very simple. Suppose, I set a threshold of value 100. Pixels have an intensity from 0 to 255. So, the pixels below 100, take a value of 0 (the dark region) and the pixels having an intensity greater than 100 take a value of 1 (the white region).

### How to Apply Threshold to an Image?

We apply thresholding to an image using the cv2.threshold() function.

**Note:** To apply threshold, the input image must be Grayscale. You can achieve that using the Program 2 we saw earlier. 

The **syntax** for threshold is as follows:

cv2.threshold(source, thresholdValue, maxVal, thresholdingTechnique)

**Parameters:**

**source:** Input grayscale Image <br>
**thresholdValue:** value of threshold above and below which thresholding will take place<br>
**maxVal:** Maximum value that can be applied to a pixel for thresholding<br>
**thresholdingTechnique:** the type of thresholding 

**Example:**

```
#applying threshold to grayscale image
cv2.threshold(grayImg,150,255,cv2.THRESH_BINARY)
```

### Let's See Threshold in Action:

![Source code for Applying threshold to an image using Python Opencv](https://cdn.hashnode.com/res/hashnode/image/upload/v1611864839485/EuDJGmuaz.png)

You can directly download the source code & image to apply thresholding from [here](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Thresholding%20an%20image.py)

Congratulations! You did it🥳 You have conquered the basic programs you are going to need to battle in the Computer Vision world👁 Today, you understood the importance of Resizing, Grayscaling, Blurring and Thresholding an image and wrote your very own programs to implement these techniques 💯 

If you think this article provided value to you, smash that like button and share it with as many friends as possible because up next, we have very some very exciting builds coming up including Face Recognition, Moving object detection, Emotion Recognition, Document Scanner and much more🔥 Don't forget to subscribe to the newsletter and never miss another value bomb 💣

### Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Creative Beginner-Level Python Projects🐍?: Check out the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y)😍

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the  [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- Wanna Interact With Me 🙋🏻‍♂️? Connect With Me on Your Favourite Platform [Here](https://theinsightfulcoder.com/contact-me)  🤝🏻

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁