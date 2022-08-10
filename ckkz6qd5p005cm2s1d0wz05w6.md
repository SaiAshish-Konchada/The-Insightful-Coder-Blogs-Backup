## The Easiest Guide to Get You Started on Computer Vision

Computer Vision is one of the hottest topics in Artificial Intelligence. From Cancer Detection to Self-Driving Cars, Computer Vision finds an application in many important aspects of our daily lives. In this article, I take you through the journey of understanding Computer Vision, selecting a programming language, and actually getting started with your first Computer Vision Program. 

## 1. Understanding Image Recognition, Image Processing, and Computer Vision

Humans have eyes to see an image, the brain to process that image and recognize what we are looking at. While a machine can accomplish marvelous feats, it fails at the most basic tasks carried out by a human being. 

![Ball](https://cdn.hashnode.com/res/hashnode/image/upload/v1611759601851/KFnvWlP5f.jpeg)

Look at his object above. What is it? Yes, it's a ball. But how did we identify that this image was of a ball? Or how do we recognize any object? 

![Process of identifying a ball by a human](https://cdn.hashnode.com/res/hashnode/image/upload/v1611760352954/1mIYO2Rj9.png)

On a very fundamental level, it is via its characteristics.  Our brain automatically extracts the features of what we see. Through experience and teachings, we know that a particular object is classified as a ball if it is a round object (mostly spherical). It has a three-dimensional structure, symmetrical in shape, has a surface area and volume based on its radius. It does not contain any faces, corners, or edges. But not all spheres are balls — it can be a globe or an orange too! The other characteristics, such as the color, texture, size, angle, and lighting, give our brain the additional information it needs to identify a ball. 

All this processing, this computation takes merely a second for our brain to execute. This is the power of the human mind. On the contrary, a machine is still way behind to catch up with this form of intelligence. In fact, we are just getting started on making machines capable of recognizing images.

### How Do Machines Recognize Images?

![Process of identifying a ball by a machine](https://cdn.hashnode.com/res/hashnode/image/upload/v1611760917512/VGOmwhIkr.png)

Apparently, a human *sees* an image through his *eyes*, *processes* the image via its *brain* and *communicates* it using his *mouth*.

Similarly, we have developed various sensors—like camera lenses to *see* an image and algorithms(step by step instructions to accomplish a particular task) to process an image.

This process of recognizing images is called **Image Recognition**. The processing we do to enhance the quality of an image is called **Image Processing**. Letting computers extract useful information from the image by imitating human vision and act on it is called **Computer Vision**.

Now that we are clear on the terminologies let's begin our journey and unlock the maximum potential of Computer Vision👁 

## 2. Selecting a Programming Language for Computer Vision:

![Python: The Best Programming Language for Computer Vision](https://cdn.hashnode.com/res/hashnode/image/upload/v1611759183777/J1AKRUkDE.png)

For this series, I am going to use Python, and I recommend it because:

a. **Easy to learn:** Writing a program in Python is like writing English. Python is very easy to learn, and even non-technical people can get the hang of it in weeks.

b. **Powerful libraries:** Python has powerful libraries(chunks of codes) that are available readily for our use. Imagine it as cooking Maggi. You already have the noodles fried and the tastemaker ready. All you've to do is mix the ingredients and boil it for two minutes. As simple as that!

c. **Free:** Python is an open-source programming language, which means it is free of cost, and everyone can contribute to its code to improve its functionality. This feature evolves Python's functionalities from time to time, which is not the case in other languages.

## 3. What is OpenCV?

![OpenCV Python Library for Computer Vision and Image Procesing](https://cdn.hashnode.com/res/hashnode/image/upload/v1611757135399/2JxAVKAY7.png)

For Computer Vision, we have a Python library called [OpenCV](https://pypi.org/project/opencv-python/). OpenCV is open source, used by over 9 million people, and funded by companies like Google, Intel, and AMD. Moreover, you can use it for commercial applications without making your project open source.

## 4. Time To Code: Loading, Saving, and Displaying an Image

![The Insightful Coder: Time to Code](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

You can find all the source code for this project at my [GitHub Repository](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Loading%2C%20Saving%20%26%20Displaying%20an%20Image.py).

We have gathered enough intel. It's time to see some action!

To install OpenCV in your system, you've to install Numpy because OpenCV uses it in the background. We will also install matplotlib for features of image display. Go to your terminal and enter:

 ```
pip install numpy
pip install opencv-python
pip install matplotlib
```
This will install the required libraries into your environment.

Let's write a basic program in Python where we load the file into our environment, save it and display it on the computer screen.

The first step is to import cv2. cv2 is an interface of OpenCV that we need to load in our environment to access its features. We do that using the ```import``` statement.

```
# Importing the required library 
import cv2
```
To **load an image** into our system, we use the ```imread()``` function of OpenCV. 

**Syntax of imread():**

cv2.imread(path, flag)

**Parameters:**

**path:** the address where the image is stored at 

**flag:** the mode in which the image should be read. Its default value is cv2.IMREAD_COLOR, meaning it will read a color image by default

Let's store this image in a variable called ```image```

```
# Loading the image
image = cv2.imread("Sample Image.jpg")
```

**Note:** If you have the image in the same location as the Python file, you do not have to provide the full path. If you wish to use an image stored in other directories, copy the path with the name and extension and replace it with Test Image.png. In Windows, the path will look something like this *D:\Photos\Test Image.png* Add an extra '\' so that Python doesn't treat it as an escape character. The final path looks like *D:\\Photos\\Test Image.png* For Linux and MAC, you can use the path directly as it appears on the address bar.

Usually, we apply different transformations to an image and save it. As we'll be exploring the image processing programs in an upcoming article today, let's just save a copy of the python image in the same directory.

To **save an image**, we use OpenCV's ```imwrite()``` function.

**Syntax of imwrite():**

cv2.imwrite(filename, image)

**Parameters:**

**filename:** the file's name to be saved with the required extension, e.g., jpg, png, jpeg. 

**image:** the image that is to be saved.

To save a copy of the image, we'd use:

```
# Saving a copy of the image
cv2.imwrite("Sample Image Copy.jpg", image)
```

To **display an image**, we use the ```imshow()``` function as, 

**Syntax of imshow():** 

cv2.imshow(window_name, image)

**Parameters:**

**window_name:** name of the window in which image the image is displayed 

**image:** the image that is to be displayed.

```
# Displaying the image
cv2.imshow("Sample Image",image)
```
If you run the program at this stage, you'll notice that the image appears for a second and disappears. That is because we did not instruct Python to give us time to view the image. To view an image for a particular duration, we use the waitKey() function.

**Syntax of waitKey():**

cv2.waitKey([delay])

**Parameter:**

**delay:** time in milliseconds 0 is the special value that means “forever." If we use 0, then the image will be displayed on the screen forever until we press a key or close the window. 

```
# Wait and display the window until a key is pressed
cv2.waitKey(0)
```

For good coding practice, we use the ```destroyAllWindows() ``` function. This destroys all the open windows when you exit the program.
```
# destroy all windows
cv2.destroyAllWindows() 
```

### The Final Source Code Looks Like This:

![Code for Loading, Saving, and Displaying an Image using OpenCV Python Library](https://cdn.hashnode.com/res/hashnode/image/upload/v1612378676385/ENQCBu0mF.png)

Congratulations, you have taken the first step into entering the world of Computer Vision!

## Through this article, you understood:

- The Concept of Computer Vision
- The Terminologies associated with Computer Vision
-  Selecting a Programming Language for coding Computer Vision Applications
- Explored the OpenCV library
- Wrote your First Computer Vision Program

You can directly download the entire source code from my [GitHub Repository](https://github.com/SaiAshish-Konchada/Artificial-Intelligence/blob/main/Computer%20Vision/Loading%2C%20Saving%20%26%20Displaying%20an%20Image.py). Make sure to star the repository while you are out there.

Continue your learning journey - [Basic Programs on Computer Vision](https://theinsightfulcoder.com/basic-programs-on-computer-vision).

Did you know, that I'm also available on Twitter? Follow me for daily value bombs, insightful threads, and plenty of useful resources!

%[https://twitter.com/InsightfulCoder/status/1399689062718578688]