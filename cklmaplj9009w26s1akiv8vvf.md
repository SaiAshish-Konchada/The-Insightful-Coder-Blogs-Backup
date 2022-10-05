## How to Build an Alarm Clock Using Python

Welcome to the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y) 🙋🏻‍♂️

I'm  [Sai Ashish](https://www.linkedin.com/in/sai-ashish/) and today, we are going to build an alarm clock using Python which plays your favorite song when the time is up 🎼

How cool is that? Tick, tick, tick. Let's start building 🚀

## Through This Project, You're Going to Learn About:

```
1. The Playsound Module
2. The Datetime Module
3. Basics of Python: Conditional Statements, Iterative Statements & Slicing a string 
4. Implementation of Your Very Own Alarm Clock
```

You can access the basics of python used in this project [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/Alarm%20Clock). Don't forget to smash the star button if it provided value to you 💯

## Step 1: Modules Required:

### 1. What is the Playsound module?

For this project, we would be using the Playsound module. Playsound is a pure Python, cross-platform, single function module with no dependencies for playing sounds. In other words, you can play a sound with just a single line of code.  The Playsound module lets us play our favorite song with just one line of code!


Playsound is not available by default in the Python Standard Library and has to be installed. To do this, we will use pip, the standard package manager for Python. All you've to do is, go to the and terminal and run:

```
pip install playsound
```

You can access the official documentation of Playsound Module from  [here](https://pypi.org/project/playsound/)

### 2. What is the Datetime Module?

A date in Python is not a data type of its own, but we can import a module named datetime to work with dates as date objects.

**Example:** Import the datetime module and display the current date:

```
import datetime

x = datetime.datetime.now()
print(x)
```

When we run the above code snippet, we obtain the output as:

```2021-01-21 00:01:15.165663```

The date contains year, month, day, hour, minute, second, and microsecond.

You can access the official documentation of the Datetime module from  [here](https://docs.python.org/3/library/datetime.html) to know more about it.

Source:  [W3Schools](https://www.w3schools.com/python/python_datetime.asp) 

## Step 2: Time to Code!

![The Insightful Coder: Time to Code](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

The first step is to import the required modules into our environment. To do that we type: 

```
#importing the required modules
from datetime import datetime   
from playsound import playsound
```
Next, we need to ask the user for the time he wants to set the alarm.

```
alarm_time = input("Enter the time of alarm to be set:HH:MM:SS AM/PM\n")
```

At this stage, we have obtained a point of time in the format of HH:MM: SS AM/PM. To compare this format of time with the system time in our computer, we need to extract the hours, minutes, seconds, and period from the above string. We achieve this using string slicing. 

String slicing helps you obtain a part of a word/sentence. Let's assume the example:

```
s = "The Insightful Coder"
print(s[4:11])
```
Taking the first index as 0, slicing prints the characters from position 4 to position 11 (not included).

```
Output:
Insight
```
Mini- Challenge🧠

Do you think you can now obtain hours, minutes and seconds from the string HH:MM:SS? Try [here](https://www.w3schools.com/python/trypython.asp?filename=demo_string2). 

Answer Reveal 🔓
```
#obtaining the hour
alarm_hour=alarm_time[0:2]

#obtaining the minute
alarm_minute=alarm_time[3:5]

#obtaining the second
alarm_seconds=alarm_time[6:8]

#obtaining the period
alarm_period = alarm_time[9:11]
```
Kudos to all the insightful coders who dared to try 🥳

Next, let's inform the user his alarm was set.

```
print("Alarm Set!")
```
All we have to do now is compare and find when the current time matches the alarm time set by the user. To check every instant of time, we will make use of the While loop. 

```
while True:
```

Inside this loop, we would first acquire the current time and store it inside a variable. 

```
now = datetime.now()
```

The current time obtained is not in the string format. To obtain a string from a datetime object we make use of the strftime() method. Obtaining the hour, minute and seconds of current time:

```
current_hour = now.strftime("%I")
current_minute = now.strftime("%M")
current_seconds = now.strftime("%S")
current_period = now.strftime("%p")
```

 %I, %M, %S etc. are format codes. The strftime() method takes one or more format codes as an argument and returns a formatted string based on it. Read more about it [here](https://www.programiz.com/python-programming/datetime/strftime).

We have both the strings now. Let's compare it:

```
if(alarm_period==current_period and alarm_hour==current_hour and alarm_minute==current_minute and alarm_seconds==current_seconds):
```
Once, the time is up, we print a message saying, "Wake up!" and play a song. Let's see it in action.

```
print("Wake Up!")
playsound('/path/to/a/sound/file/you/want/to/play.mp3')
```
Finally, we break out of the loop using the break statement.

```
break
```
The Final Source Code Could Be Seen Below:

![Source code of building an alarm clock using python](https://cdn.hashnode.com/res/hashnode/image/upload/v1611258436851/-VRByMBWX.png)

That's it, folks! You now have built your very own alarm clock using just 18 lines of code 👩🏻‍💻 You can download the source code to this project [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/Alarm%20Clock). Do hit the twinkle star, if this article provided value to you 🔥

And while you're at it, consider giving this blog the maximum love you can and I promise to give you such value bombs every week 💣 Until then, take care 🙋🏻‍♂️

## Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- Wanna Interact With Me 🙋🏻‍♂️? Connect With Me on Your Favourite Platform [Here](https://theinsightfulcoder.com/contact-me)  🤝🏻

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁