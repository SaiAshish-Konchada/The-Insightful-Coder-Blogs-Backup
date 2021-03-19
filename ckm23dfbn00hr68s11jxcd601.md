## 5 Python Projects That Can Be Built Under 5 Minutes

Welcome to the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y) 🙋🏻‍♂️

I'm  [Sai Ashish](https://www.linkedin.com/in/sai-ashish/)  and today, we are going to code 5 Python Projects that can be built in under 5 minutes 🤯

I hope you're psyched because this is going to be amazing 💯

## What Are We Going to Build?

```
1. Notification Generator 🔢 
2. Check Your Battery Percentage 🔋
3. Take a Screenshot 🖼
4. Figlet Generator 🔠
5. ConvertText to Speech 🗣
```

## What Are We Going to Learn Today?

```
1. How to effectively use modules in our python programs
2. Basics of Python: Functions
```

## Project 1: Notification Generator 🔢

As the name suggests, a notification generator generates a notification(a message) about a particular task, reminder or anything you require. In today's build, we would be generating a pop-up notification on a Windows device.

Apart from the obvious, you can integrate this snippet of code into any of your applications. For example, in  [How to Build an Alarm Clock using Python](https://theinsightfulcoder.com/how-to-build-an-alarm-clock-using-python), you can also generate a notification along with your favourite song. Or suppose you wanted to get an alert whenever your battery percentage is below 35 or get reminders, this is the tool for you.

### Let's Have a Look at Our Build:

![Notification Generator Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1615287211039/1noLX5aTw.png)

### Module Used:

For this build, we require the win10toast module. win10toast is an easy-to-use Python library for displaying Windows 10 Toast(Pop-up) Notifications. The official document of the module can be accessed from [here](https://pypi.org/project/win10toast/). 

To install the win10toast module, go to the terminal and run,

```
pip install win10toast
```
That's it. You're all ready for the build now. 

### Time to Code!

The first step is to import the win10toast module into our programming environment. For this, we use the import statement as,

```
from win10toast import ToastNotifier
```

Next, we define a function named windows_popup that takes three parameters as input — title, content and duration. 

```
def windows_popup(title,content,duration=10):
```

Functions help break our program into smaller and modular chunks. Moreover,  it avoids repetition and makes the code reusable.

In our function, we code two statements,

```
toast=ToastNotifier()
toast.show_toast(title,content,duration=duration)
```

We create an instance of the ToastNotifier class and store it inside toast variable. Imagine the instance as a remote control to your program. You can now use any buttons on the remote control to perform the task needed.

We call the show_toast function and pass the input parameters as seen. 

**Parameters:**

**title:** the title of the notification. it appears in bold. Example: Reminder <br>
**content:** the content of the notification. Example: Close down your desktop and go for a walk!<br>
**duration:** the duration in seconds you want the notification to be shown on the screen<br>

Finally, we call the function as:

```
windows_popup("Reminder", "Go and get a life!")
```

### Final Source Code for Notification Generator is seen below:

![Final Source Code for Notification Generator Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1615290608859/M139Ql1_F.png)

You can directly download the source code for Notification Generator from my [Github Respository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20Python%20Projects%20in%205%20mins/Windows%20Notification.py).

## Project 2: Check Your Battery Percentage 🔋

In this build, we generate the battery percentage of our device. 

### Module Used:

For this build, we use the psutil module. psutil is a cross-platform library for process and system monitoring in Python. The official documentation of the psutil module can be found  [here](https://pypi.org/project/psutil/).

To install psutil into our system, type in the terminal the following:

``` 
pip install psutil
```
### Time to Code!

As always, import the psutil module into our environment.

```
import psutil
```

Gain the remote control by creating an instance of the sensors_battery() class in the psutil module.

```
battery = psutil.sensors_battery()
```

Gain the battery percentage information into variable percent as follows:

```
percent = str(battery.percent)
```

To display the battery percent on the screen, type:

```
print("Battery Percent= " + percent + "%")
```

### Final Source Code for Battery Percentage Checker:

![Final Source Code for Battery Percentage Checker Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1615280988308/qfcrYJIC0.png)

You can directly download the Battery Percentage Checker code from my  [Github Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20Python%20Projects%20in%205%20mins/Battery%20Percentage.py) too. 

To **test** your coding skills, **try generating a notification when the battery percentage falls below 35%**. Comment your code in the comment box below!  

## Project 3: Take a Screenshot 🖼

### Modules Required:

For this build, we require the Pyautogui and the time module.

PyAutoGUI is a python module that lets you control your mouse and keyboard using a program. PyAutoGUI also lets you automate your everyday tasks and can play games, login into emails, and more. You can access the official documentation of Pyautogui module from  [here.](https://pyautogui.readthedocs.io/en/latest/) 

To install PyAutoGUI in your system, open your terminal and run:

```
pip install pyautogui
```
The time module provides various time-related functions. We use it to retrieve the system time and display it on the screen. You can access the official documentation from [here](https://docs.python.org/3/library/time.html) 

### Time to Code!

Importing the required modules into our python environment:

```
import pyautogui
import time
```
We use the time.sleep method to switch the application from our python environment to the screen we want to take a screenshot from. 

```
time.sleep(3)
```

To take the screenshot, we use pyautogui's screenshot method and store it inside the img variable.

```
img = pyautogui.screenshot()
```
To save the image, we use the save method as:

```
img.save(r"image.png")
```
**Note:** This command will save the image into the same directory as the location of the python file you're running from. 

### Final Source Code for Screenshot Taker is as follows:

![Screenshot Taker Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1615281083523/8Kcd6JxTy.png)

You can directly download the source code of the Screenshot Taker build from  [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20Python%20Projects%20in%205%20mins/Screenshot.py).

## Project 4: Figlet Generator 🔠

The Figlet Generator Converts ordinary text into a creative figure letter design(ASCII Art Font) as shown below:

![Figlet output image](https://cdn.hashnode.com/res/hashnode/image/upload/v1615295031876/IlBNhjXYS.png)

### Modules Required:

For this build, we require the PyFiglet module. You can access the official documentation of Pyfiglet module from  [here](https://pypi.org/project/pyfiglet/0.7.4/).  The PyFiglet module can be installed by using: 

```
pip install pyfiglet
```
### Time to Code!

The first step is to import the Pyfiglet module

```
import pyfiglet 
```  

To convert your word into ASCII Block Art format we use the figlet_format function. We store the result into a variable called result. For slant font, we set the font to slant. For a normal block, just omit that parameter and enter only the text in double-quotes.

```
result = pyfiglet.figlet_format("Sai Ashish", font = "slant")
```

Display your creativity using the print statement:
```
print(result) 
```
### Final Source Code for Figlet Generator:

![Final Source Code for Figlet Generator:](https://cdn.hashnode.com/res/hashnode/image/upload/v1615295943054/wfmo44t5k.png)

You can directly download the source code from my [Github Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20Python%20Projects%20in%205%20mins/Figlet.py).

## Project 5: Convert Text to Speech 🗣

Last but not the last and my most favourite build among all, the Text to Speech Generator. 

### Module Required:

For this amazing build, we require the pyttsx3 module. pyttsx3 is a text-to-speech conversion library in Python. Unlike alternative libraries, it works offline and is compatible with both Python 2 and 3.You can check the official documentation from  [here](https://pypi.org/project/pyttsx3/) 

To install pyttsx3 into our system, go to the terminal and type:

```
pip install pyttsx3
```

### Time to Code!

We import the pyttsx3 module into our environment using:

```
import pyttsx3
```

To get the remote control, we initialise pyttsx3 as:

```
engine = pyttsx3.init()
```

After gaining the instance, we use the say method to tell the engine to speak the sentence provided to it.
 
```
engine.say("Hello Everyone")
```

Finally, we use the runAndWait command to run the command.

```
engine.runAndWait()
```

### Final Source Code for Converting Text to Speech:

![ Final Source Code for Converting Text to Speech:](https://cdn.hashnode.com/res/hashnode/image/upload/v1615281332431/PmolIqy6E.png)

You can directly download the Text to Speech Build from my  [Github Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20Python%20Projects%20in%205%20mins/Text%20to%20Speech.py).

That's it, folks! We have successfully learnt 5 short yet interesting builds that can be implemented in under 5 minutes. These builds are a very good stepping step for any beginner in Python. If this blog provided value to you smash the like button and subscribe to the newsletter to never miss another blog update 💯

## Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- I'm also dropping daily value bombs and development insights on my  [Instagram](https://www.instagram.com/theinsightfulcoder/) Page. Make sure to follow me up 💯

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁