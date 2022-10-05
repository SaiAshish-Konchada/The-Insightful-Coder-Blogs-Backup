## How to Build a Digital Time Clock Using Python

Welcome to the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y) 🙋🏻‍♂️

I'm  [Sai Ashish](https://www.linkedin.com/in/sai-ashish/)  and today, I'm going to show you how to build a live digital clock using Python with just 12 lines of code😍

How exciting is that? Let's get started 🚀

## What Are We Going to Build?
 
![Live GUI Digital Clock Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1611257903230/XM3h6Fsb3.gif)
This amazing digital clock ⏰

## What Are We Going to Learn Today?

```
1. Tkinter & Time Module
2. Basics of Python: Functions
3. Creating a Tkinter Window, Giving Title to the Window, 
   Setting Background & Setting Label
4. Implementation of the Digital Clock With Detailed Explanation
```
You can access the exclusive theory used in this project [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/Digital%20Clock). Don't forget to smash the star button if it provided value to you 💯

## Step 1: The Design

Hold on! Hold on! Before diving into the development part, an insightful coder must have a clear idea of the project he is going to make. To keep it as simple and elegant as possible, I planned a rectangular digital clock with a black background, white text, and the HH:MM:SS time format. You can choose to add AM/PM as per your liking. 

## Step 2: Modules Required:

### 1. What is the Tkinter module?

For this project, we would be using the Tkinter module. Tkinter is a Python binding to the Tk GUI toolkit. It is the standard Python interface to the Tk GUI toolkit and is Python's de-facto standard GUI. You can access the official documentation of Tkinter Module from  [here](https://docs.python.org/3/library/tk.html). 

### 2. What is the Time Module?

The time module provides various time-related functions. We use it to retrieve the system time and display it on the screen. You can access the official documentation form  [here](https://docs.python.org/3/library/time.html)📄 

## Step 3: Time to Code!

![The Insightful Coder: Time to Code](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

The first step is to import everything(all classes, functions, and variables) stored inside Tkinter to our program file. To do that we type: 

```
from tkinter import *
``` 
'*' stands for all/everything.

After importing Tkinter, I'd like to import a function called strftime from the module time. The strftime() method returns a string representing date and time using date, time, or datetime object. In simpler terms, it retrieves the system time. 

```
from time import strftime
```
Now, I want to create a window for the clock. To do that, I make use of Tk from the Tkinter module. 

```
root = Tk()  # Creates tkinter window
```
Let's give the title to the window as 'Digital Computer Clock.'

```
root.title("Digital Computer Clock")  # Adds title to tkinter window
```

Creating a function to display time on a label. For this, I will be using the Tkinter Label Widget.

```
# user defined time function
def time(): 

# fetching the system time in the desired time format and storing inside variable string
    string = strftime("%H:%M:%S %p") #%p for AM/PM
# label variable displaying time retrieved from the computer
    lbl.config(text = string)
# run the function after every 1000ms, that is 1 second
    lbl.after(1000, time)
```

Styling the label widget with font Arial, size 160, bold format, background color as black, and foreground color as white. 

```
lbl = Label(root, font = ("arial", 160, "bold"),bg="black",fg="white")
```

The pack method in Tkinter packs widgets into rows or columns. I want the content to be packed in the center, filling the entire space assigned to it both horizontally and vertically. Lastly, the expand option adds a little space to the widget box if necessary. 

```
lbl.pack(anchor = "center",fill = "both",expand=1)
```
Finally, we call the functions and run the program.

```
time()
mainloop()
```

## The Final Source Code for the Digital Time Clock Can Be Seen Below :

![Source Code for the Digital Time Clock](https://cdn.hashnode.com/res/hashnode/image/upload/v1611258278552/1WBCfr52b.png)

We did it 🥳 We have made our own digital clock with just 12 lines of code!! How amazing is that? As a gift for staying till now, you get access to my [Python For Beginners Series Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners)  😍 This repository contains all the source code you'd need to get started as a Python Developer 🐍.

You can also download the source code to this project [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/Digital%20Clock). Do hit the twinkle star, if this article provided value to you 🔥

And while you're at it, consider giving this blog the maximum love you can and I promise to give you such value bombs every week 💣 Until then, take care 🙋🏻‍♂️

## Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- Wanna Interact With Me 🙋🏻‍♂️? Connect With Me on Your Favourite Platform [Here](https://theinsightfulcoder.com/contact-me)  🤝🏻

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁