## Build & Play the Magic 8 Ball Game Using Python

Welcome to [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y)🙋🏻‍♂️

I'm [Sai Ashish](https://www.linkedin.com/in/sai-ashish/) and today, I'm going to show you how to build the traditional Magic 8 ball game using Python😍

How psyched are you for this build? Let's get started 🚀

## What are we going to learn today?

```
1. What is the Magic 8 Ball game?
2. Internal Mechanism of Magic 8 Ball
3. The Random Module, the Time module & the Pyfiglet Module
4. Basics of Python: Functions & Recursive Function
5. Implementation of Magic 8 Ball Game using Python with a detailed explanation
```

## 1. What is Magic 8 Ball Game?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1612022890401/h9mzzLvfG.png)

The Magic 8-Ball is a plastic sphere, made to look like an eight-ball, that is used for fortune-telling or seeking advice. The user asks a yes–no question to the ball, then turns it over to reveal an answer in a window on the ball🎱

Source:  [Wikipedia](https://en.wikipedia.org/wiki/Magic_8-Ball) 

## 2. Internal Mechanism of Magic 8 Ball

Let me tell you a secret real quick🤫 In reality, the Magic 8 Ball, just picks out random answers from a pool of possible answers embedded into it. There is no actual processing involved. In this build, we are going to achieve this magic using the Random module. 

## 3. The Random Module, the Time module & the Pyfiglet Module

### a. The Random Module

To help us build this game, we are going to use an amazing module of Python called random. The random module generates random numbers for us. This gets in real handy as we do not want our computer to be biased.

### b. The Time Module

The time module provides various time-related functions. We use it to retrieve the system time and display it on the screen. You can access the official documentation form [here📄](https://theinsightfulcoder.com/how-to-build-a-digital-time-clock-using-python)
### c. The Pyfiglet Module

Before we dive into the build, I'd like to introduce everyone to an aesthetic module of Python, The Pyfiglet Module. *Aesthetic module? What do you mean?* 

Yes, aesthetic. The Pyfiglet Module converts ordinary looking text into creative word blocks in just a line of code. An example of this can be seen in the image below:

![Magic 8 Ball Ascii Art](https://cdn.hashnode.com/res/hashnode/image/upload/v1612023976243/g9WzNqpME.png)

To install pyfiglet into our system, open your terminal and type the following command:

```
pip install pyfiglet
```


## 4. Time To Code
![Time to Code, The Insightful Coder](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

The first step is to import the required modules:

```
# importing the required libraries
import random
import pyfiglet
import time
```

Let's define a function named magic8ball() which greets the players of the game and takes their name as an input.

We define a function by using the define statement as:

```
# defining function magic8ball()
def magic8ball():
```

Inside this magic8ball() function, let's print the amazing Magic 8 Ball design we created earlier using the Pyfiglet module. 

```
# print aestheic text design
print(pyfiglet.figlet_format("Magic 8 Ball"))
```
Asking the player for their name:
```
# asking for player's name
name = input('Hey there, I am the Magic 8 Ball, What is your name?')
```
Greeting the player:
```
# greeting the player
print('Hello ' + name + '!')
``` 
Inside this function, let's call another function called magic_questions()
```
# calling the magic_questions() function to ask for question and give magic response
magic_questions()
```
The process of calling one function inside of another function is called Recursion.

Let's define  magic_questions()
```
# defining the function magic_questions()
def  magic_questions():
``` 
Inside the magic_questions() function, we store the 20 default answers originally stored inside of the Magic8Ball inside a variable called ```answers```. The random module will choose one of the answers by itself and display it to the player.
```
# list of answers the ball replies
 answers = ["It is certain", "It is decidedly so", "Without a doubt", "Yes, definitely",
               "You may rely on it", "As I see it, yes", "Most Likely", "Outlook Good",
               "Yes", "Signs point to yes", "Reply hazy, try again", "Ask again later",
               "Better not tell you now", "Cannot predict now", "Concentrate and ask 
                again", "Don't count on it", "My reply is no", "My sources say no", "Outlook 
                not so good", "Very Doubtful"]
```
Now, we want to ask the user to input his question for the purpose of fortune-telling/ advice seeking. Sadly, the answers are random and not related to the questions in any manner. Therefore, we would ask the users for input but wouldn't store it anywhere.

```
input('Ask me a question ')
```
To simulate the feeling of a real game, let's add some text and a delay between them so that it seems that the computer is actually thinking and generating the possible answer!
```
# simulating the thinking process
print("Thinking...")
time.sleep(1)
print("Gathering possible answer...")
time.sleep(2)
```

The answer is picked out at random. We use the randint() function of random to pick out the answers.
```
# printing out a random answer from the list of possible answers
print (answers[random.randint(0, len(answers)-1)] )
```

After a delay of 3 seconds, we ask the player if they want to play again. The replay will be taken care of by the Replay() function we are about to define next.

```
time.sleep(3)
# calling the Replay to check if the player wants to play again
Replay()
```

Defining the function Replay():

```
# defining the Replay function()
def Replay():
```

We ask the player if they want to play again and store the response in lowercase using the lower() function.

```
# asking the player's interest in playing again
print ('Do you have another question? [Yes/No] ')
# converting the response to lower case to avoid capitalisation issues
reply = input().lower()
```
If the user wants to play again, we redirect him to the magic_questions() function and the game resumes the same from that point. If no, we'd stop the execution of the program using the exit() function. If the user enters anything else, we ask the user to re-enter his choice as it wasn't clear. The benefit of using the lower) function in the above line was that if the player inputs their response but is clumsy about the capitalisation, it could be taken care of.  
```
# if yes, resume the game again from the question-answer part
if reply == 'yes':
    magic_questions()
# if no, stop the execution of the program
elif reply == 'no':
    exit()
# in case of an invalid response, ask the player to enter a valid choice
else:
    print('Apologies, Please enter Yes or a No.')
    Replay()
```
Finally, we call the magic8ball() function to execute our game.
```
# calling the magic8ball() function to recursively activate the other functions too
magic8ball()
```

## Final Source Code for the Magic 8 Ball Build🎱


![Final Source Code for the Magic 8 Ball Build using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1616935044771/sGCS66L3E.png)

Let's try the game out!

## Output for the Magic 8 Ball game🎱

![Output for the Magic 8 Ball game using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1616936013176/4Qiq5hDgi.png)

That was demeaning 😂 Atleast, my articles would provide value to the amazing people out there 💯

In this build, we've extensively used the power of recursion. We've divided our program into small chunks, each to carry out a particular task. In addition, we've recursively called functions within functions to kind of automate the flow of our program. Instead of a loop, we directly call the magic_questions() function if the player wants to play again.  

You can directly download the Source Code to this build can be downloaded from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/blob/main/Magic%208%20Ball/magic8ball.py). 

And while you're at it, consider giving this blog the maximum love you can and I promise to give you such value bombs every week 💣 Until then, take care 🙋🏻‍♂️

### If you liked this article, I'm sure you'd love these too:

- [5 Python Projects That Can Be Built Under 5 Minutes](https://theinsightfulcoder.com/5-python-projects-that-can-be-built-under-5-minutes) 🔢
- [Build a Message Bomber Using Python in Just 6 Lines of Code](https://theinsightfulcoder.com/build-a-message-bomber-using-python-in-just-6-lines-of-code) 📧
- [How to Build a Guessing Number Game Using Python](https://theinsightfulcoder.com/how-to-build-a-guessing-number-game-using-python) 🤔
- [How to Build a Digital Time Clock Using Python](https://theinsightfulcoder.com/how-to-build-a-digital-time-clock-using-python) ⏲
- [How to Build an Alarm Clock Using Python](https://theinsightfulcoder.com/how-to-build-an-alarm-clock-using-python) ⏳
- [How to Build an URL Shortener & Expander Using Python](https://theinsightfulcoder.com/how-to-build-an-url-shortener-and-expander-using-python) 🔗