## 5 More Python Projects That Can Be Built in Under 5 Minutes

While learning a new programing language, people tend to be confused about which project to start with. Or they're often excited to start building some cool projects but realise that they spent weeks learning concepts but have no hands-on experience Continuing the success of my  [previous article](https://theinsightfulcoder.com/5-python-projects-that-can-be-built-under-5-minutes)  with the same title, I present to you— 5 More Python Projects That Can Be Built in Under 5 Minutes.

## What Are We Going to Build?

```
1. IP address fetcher
2. BMI Calculator
3. Map Generator from Location
4. Zip and Unzip Files
5. Text Translator
```

## What Are We Going to Learn Today?

```
1. How to effectively use modules in our python programs
2. Basics of Python: Functions
```
## Project 1: IP Address Fetcher

As the name suggests, we are going to build a Python program that would fetch the name and IP address of our device. 

### Module Used:

For this build, we'll use the socket module. A socket acts as a node( a point of connection) is used to messages across a network. You can access the documentation of the socket module from  [here](https://docs.python.org/3/library/socket.html).

### Time to Code!

The first step is to import the module into our Python environment.
```
import socket
```

We can get the hostname of our device using the gethostname() method. We'll store the result obtained in a variable called hostname.
```
hostname = socket.gethostname()
```
To get the IP address of our device, we have to pass the hostname through gethostbyname() method.
```
IP = socket.gethostbyname(hostname)
```

We've the hostname. We've the IP address. All that's left is to display it.
```
print("Computer Name:" + hostname)
print("IP address:"+IP)
```

### Final Source Code for IP Address Fetcher:

![Final Source Code for IP Address Fetcher using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618519194721/Vtj4eyDQr.png)

### Output for IP Address Fetcher:

![Output for IP Address Fetcher Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618519293661/9OhAY1yIUk.png)

You can directly download the source code for IP Address Fetcher from my  [Github Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20More%20Python%20Projects%20in%205%20Minutes/IP%20Address%20Fetcher.py). 

## Project 2: BMI Calculator

BMI or Body mass index is a measure of body fat based on height and weight that applies to adult men and women. In this project, we are going to calculate the BMI using height in centimetres and weight in kilograms. We don't require any modules for this build.

### Time to Code!

The first step is to ask the height and weight of the person as specified.

```
height = float(input("Enter your height in cm: "))
weight = float(input("Enter your weight in kg: "))
```
Calculate the BMI of the person using the formula,

BMI = height in m/ (weight in kg)<sup>2</sup>

```
BMI = weight / (height/100)**2
```
We divide the height by 100 to convert centimetres to meters and square the weight by using the exponential operator **.

We use String interpolation to display the BMI of the person. Interpolation or interpolate means insert (something of a different nature) into something else. That is inserting/replacing the value of the variables inside the statement of the string we are going to display. We use this as, 

```
print(f"You BMI is {BMI}")
```
As per the chart obtained in  [U.S. Department of Health & Human Services](https://www.nhlbi.nih.gov/health/educational/lose_wt/BMI/bmi-m.htm), the BMI Categories are as follows:

Underweight = < 18.5       <br>
Normal weight = 18.5–24.9 <br>
Overweight = 25–29.9 <br>
Obesity = BMI of 30 or greater 

We'll use conditional statements if-else to compare the above construct.

```
if BMI < 18.5:
    print("You are underweight.")
elif BMI <= 24.9:
    print("You are healthy.")
elif BMI <= 29.9:
    print("You are over weight.")
else
    print("You are obese.")
```

### Final Source Code for BMI Calculator is:

![Final Source Code for BMI Calculator using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618520856329/qTinvTLqB.png)

### Output for BMI Calculator:

![Output for BMI Calculator using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618520990012/LmehuOPnR.png)

You can directly download the source code for BMI Calculator from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20More%20Python%20Projects%20in%205%20Minutes/BMI%20Calculator.py).

## Project 3: Map Generator from Location

In this project, we'll generate a map from the location coordinates using Python. 

### Module Required:

For this build, we require the Folium module. Folium is a Python library used for visualizing geospatial data. You can access the official documentation of Folium from  [here](https://pypi.org/project/folium/). To install folium, visit your terminal and type,
```
pip install folium
```
### Time to Code!

The first step is to include the module in our Python Environment. We do that using the import statement.
```
import folium
```
We accept the latitude and longitude coordinates of any place we want to visualise. I want to visualise my city, Mumbai. I enter the coordinates as,
```
map = folium.Map(location=[19.0760, 72.8777])
```
Finally, we save the build as an HTML file as.
```
map.save("My Location.html")
```
### Final Source Code for Map Generator from Location:
![Final Source Code for Map Generator from Location Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618576881524/KpQv4FRLY.png)

### Generated HTML Map File:
 
![Generated HTML Map File](https://cdn.hashnode.com/res/hashnode/image/upload/v1618571411762/LBGN5SVNZ.png)

You can directly download the source code for Map Generator from Location from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20More%20Python%20Projects%20in%205%20Minutes/Map%20Generator.py)

## Project 4: Zip & Unzip File

We often require to zip files for sharing multiple files via email or unzip files when downloading files from the internet. In this build, we'll build a program that does this task for us. You can even further modify the code to automate the process and unzip multiple files at once. 

### Module Used: 

For this build, we'll be using the patool module of Python. According to its  [official documentation](https://pypi.org/project/patool/), various archive formats can be created, extracted, tested, listed, searched, compared and repacked by patool. The advantage of patool is its simplicity in handling archive files without having to remember a myriad of programs and options. To install Patol into your system, go to the terminal and type,

```
pip install patool
```

### Time to Code!

The first step as always is to import the required libraries. You can do it as,
```
import patoolib
```
We'll define 2 functions. The first one named Zip() to zip our files and the other named Unzip() to unzip our files. To zip our files, we've to provide the paths for our files to be zipped.

**Note:** If you have the image in the same location as the Python file, you do not have to provide the full path. If you wish to use an image stored in other directories, copy the path with the name and extension and replace it with Test Image.png. In Windows, the path will look something like this D:\Photos\Test Image.png Add an extra '\' so that Python doesn't treat it as an escape character. The final path looks like D:\Photos\Test Image.png For Linux and MAC, you can use the path directly as it 
appears on the address bar.

```
def Zip():
    patoolib.create_archive("file.zip",("path_to_file_1","path_to_file_2"))

def Unzip():
    patoolib.extract_archive("path_to_file_to_be_extracted",outdir="extract")
```
We use the create_archive method to zip the files. As per the above code, the function will zip both the files and save them as file.zip. Similarly, we use the extract_archive() function with the link to the zipped file to be extracted. We specify the function to store our files in a directory called extract.

All that's left to do is to invoke the functions as per the user's choice. We ask the user to input 1 to Zip and 2 for Unzip. We convert the value obtained to an integer using the int() function as by default, Python accepts values in string format. 

```
if __name__ == '__main__':
    choice=(int(input(Enter 1 for Zip & 2 for Unzip)))
```
Using the conditional statement if-else, we invoke the respective functions.
```
if choice==1:
    Zip()
else:
    Unzip() 
```
### Final Source Code for Zipping & Unzipping File:
![Final Source Code for Zipping & Unzipping File Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618569755437/z99KeIWwE.png)

You can directly download the source code for Zipping & Unzipping File from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20More%20Python%20Projects%20in%205%20Minutes/Zip%20%26%20Unzip.py).

## Project 5: Text Translator
 
Last but not the least, we'll build a Text Translator. using the text translator you can translate any sentence from one language to another.

### Module Used:

For this build, we use the translate module. As per its  [official documentation](https://pypi.org/project/translate/), this is a simple, yet powerful command-line translator with google translate behind it. 

### Time to Code!

The first step is to import the class Translator from the module translator. We do it as,
```
from translate import Translator
```
We need to specify the language we want to convert from and to in the translator function. We save the answer obtained in a variable called translator.
```
translator = Translator(from_lang="english", to_lang="chinese")
```
We pass the message to be translated into the translate function.
```
translation = translator.translate("Good Morning")
```
Finally, we display the translated message as,
```
print(translation)
```
### Final Source Code for Text Translator:
![Final Source Code for Text Translator Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618522199618/3kzQAnP0f.png)

### Text Translator in Action:
![Output for Text Translator Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1618522225463/zWO2PI6ik.png)
You can directly download the source code for Map Generator from Location from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/5%20More%20Python%20Projects%20in%205%20Minutes/Text%20Translator.py).

That's it, folks! We have successfully learnt 5 short yet interesting builds that can be implemented in under 5 minutes. These builds are a very good stepping step for any beginner in Python. If you find my content valuable and want to support my efforts, consider buying me a coffee!

<a href = "https://www.buymeacoffee.com/saiashish">
![Buy Me A Coffee](https://cdn.hashnode.com/res/hashnode/image/upload/v1618475866800/vzRVRor5z.png)
 </a>

## Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- I'm also dropping useful dev resources, interactive quizzes and Interview preparation on my  [Instagram](https://www.instagram.com/theinsightfulcoder/) Page. Make sure to follow me up 💯

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁