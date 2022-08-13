## Automating Facebook Login Using Python

In this article, we are going to automate the Facebook login process. We will achieve this using web automation, also known as browser automation. Web automation means automating, that is, performing a task automatically without the need for human effort.

## 1. The Approach of Problem-Solving via Automation

The first step in problem-solving is to** identify the root of the problem**. The problem is to perform the same login task every morning. To solve this, we need to come up with an elegant method that does this task for us. 

The most feasible solution to automate a program is by building one. I choose ** Python** as my ideal programming language for this task because of its ease and powerful libraries.

Let's list out the steps we want our program to automate:

```
Step 1: Open Google 
Step 2: Visit Facebook's Website
Step 3: Click on the input box under Email ID/Phone number
Step 4: Enter credentials
Step 5: Click on the input box under Password
Step 6: Enter the password
Step 7: Click on the login button
```

This is the algorithm for our problem statement. Now, we want to search for something that could help us perform this task. 

Open your browser, and search for "How to automate web using Python?" 

![How to automate web using Python? Google Search Results](https://cdn.hashnode.com/res/hashnode/image/upload/v1617019098487/HlNQuwtSk.png)

If you scroll down, you'd see one word popping more often than others. That's **Selenium**. The next step should be to explore more about Selenium. 

![Selenium Web Automation Tool](https://cdn.hashnode.com/res/hashnode/image/upload/v1617019251242/DeSX3Kwxnk.png)

I googled Selenium and here's what I found. **Selenium automates browsers!** Selenium is an open-source tool Web automation tool that helps users to control a web browser through a program. That's perfect. The next question was to find a way to use Selenium with Python. 

![Selenium for Python Google Search Results](https://cdn.hashnode.com/res/hashnode/image/upload/v1617019416205/B4z2TzrcP.png)

Here, I discovered the documentation of Selenium for Python. Here's the  [link](https://pypi.org/project/selenium/) .

![Installing Selenium in your Python Environment](https://cdn.hashnode.com/res/hashnode/image/upload/v1617019499484/Ucj1XyI2Td.png)

On visiting the website, I found the command to install Selenium in my Python Environment. It was ```pip install selenium```.

![Webdriver for Selenium Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1617019701577/PahGLKpJB.png)

If you scroll down, you'd encounter that Selenium requires something called a driver to interface with the browser. A **Web Driver** is an open tool used by Selenium that **establishes a connection between you and any website**. There are different kinds of driver options to choose from in accordance with the browser you want to automate. For this build, I'm going to use the Google Chrome Browser, so, I visit the site listed beside Chrome.

The site leads to the **ChromeDriver - WebDriver for Chrome** page. There are different versions of the driver available according to the version of your browser. Check the version of the browser you're using visiting the 3 dots -> Help -> About Google Chrome 

![How to find version of Google Chrome](https://cdn.hashnode.com/res/hashnode/image/upload/v1617020342020/wD7WdQJ8W.png)
![Google Chrome Version Check](https://cdn.hashnode.com/res/hashnode/image/upload/v1617020399169/R9sleXL-r.png)

As my Chrome version is 89.0.4389.90, I'd select the second option from the current releases of Chrome Driver.

![Which version of chrome web driver to install according to Google Chrome Version?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617020515431/MJ1dJLinr.png)

I'm using Windows as my Operating system, so I choose the 5th option from the list. This downloads a zip file named ```chromedriver_win32```.
 
![Downloading Google webdriver for chrome](https://cdn.hashnode.com/res/hashnode/image/upload/v1617020583700/eYHB76Kw5.png)

Extract the folder. This unravels an executable file. That's it. Now, we are ready to automate our task.

## 2. Time to Code

![Time to Code, The Insightful Coder](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

Step by step, we are going to solve each step of the algorithm we created earlier, and voila! — our build would be successful.

### **Step 1:** Open Google 

By reading the documentation, I noticed this is achieved using the webdriver.Chrome function, which means I've to import webdriver from selenium. To do that, I type:

```
# importing the required module
from selenium import webdriver
```

We'll do one more quick step here, which is storing the credentials in variables.

```
# store the credentials
user_id = "email_or_phone_number_to_your_facebook_account"
password = "password_to_your_facebook_account"
```

We have to create an object of webdriver so that we can use it as a remote control to perform any automation task we wish to. We achieve this using the webdriver.Chrome() function.

**Syntax:**
variable_name = webdriver.Chrome('path_to_chromedriver.exe_file_we_downloaded_earlier')
```
browser = webdriver.Chrome('C:\\webdrivers\\chromedriver.exe')
```
In Windows, add a double backslash as a single backslash denotes escape character. This opens up the Google website.

### **Step 2:** Visit Facebook's Website

To open Facebook we will be using the get() method. 

**Syntax:**
browser_object.get(link_of_the_webpage_to_be_opened)

You can imagine the .get as a button on a remote control that opens up any website whose URL we pass to it. To open Facebook, simply pass the URL of facebook's main page.

```
browser.get('https://www.facebook.com/')
```

### **Step 3:** Click on the input box under Email ID/Phone number

The next step is to click the input box under Email or phone. This may seem a bit tricky but if you understand the following steps in order, it'd be a piece of cake for you. 

![Login/Main page of Facebook.com](https://cdn.hashnode.com/res/hashnode/image/upload/v1617028516260/9s76UUyqD.png)
This is Facebook's main page. We click on the input element to activate it and send our credential to it. To do this first, we have to understand that a webpage is made up of something called HyperText Markup Language(HTML). The HTML decides the structure of a website. The HTML has tags(like parts of a body) and each tag can be accessed via its specific attributes(property). 

Similarly, the input field also has a tag with some attributes. To identify the name of the tag, we will inspect the code of the webpage. 

![How to inspect the source code of any web page?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617030531242/Twp6dQAbt.png)

![How to inspect the source code of any web page using Google Chrome?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617030616254/rFDCeazU7J.png)

Visit the three dots -> More tools -> Developer Tools or simple type Ctrl+Shift+I and the browser opens up a section of the code of the webpage, It may look super scary if you're unfamiliar with this, but don't worry, you don't have to understand it all. 

![How to inspect the element of the source code of any web page?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617030671351/u52RKWoi6.png)

Press Ctrl+Shift+C or click on the select button(arrow thingy). Now, if you hover over the web page different parts will start gettings highlighted. We have to click on our target element, in our case, the Email or phone input box. This opens up the corresponding source code to that element. 

![How to inspect the attribute id of any element of source code of any web page?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617030988262/ViifzzzvL.png)

It denotes that it is an input element. Note down the id attribute of the element. It is ```email```. This acts as the unique identifier for that element. In our Python Program, we will find that element using the find_element_by_id() function.

```
user_box = browser.find_element_by_id("email")
```
This finds the element with the id email and returns an object into the user_box variable.

### **Step 4:** Enter credentials

We will pass the email_id or phone stored from the program into the browser using the send_keys() function.
 
```
user_box.send_keys(user_id)  
```
### **Step 5:** Click on the input box under Password

Similarly, repeat the process to find the Password element's id. We get the id of the password input field as ```pass```.

![How to inspect the attribute id of any element of source code of any web page?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617031992753/15WxjgghW.png)

Get the object of the element using the find_element_by_id() method.
```
password_box = browser.find_element_by_id("pass")   
```

### **Step 6:** Enter the password

Pass the password stored earlier in the program using the send_keys() function.
 
```
password_box.send_keys(password) 
```

### **Step 7:** Click on the login button

Following the same process for the login button as well, but this time we'll choose the name attribute instead of the id attribute. The reason for that is it is easy to remember and the id seems to be dynamically updated every time the page is loaded, so it wasn't working out. 

![How to inspect the attribute name of any element of the source code of any web page?](https://cdn.hashnode.com/res/hashnode/image/upload/v1617041236462/b_OWIGvl7.png)

After locating the element, we'll click it using the .click function()

```
login_box = browser.find_element_by_name("login")      
login_box.click()
```

## Final Source Code for Automating Facebook Login Using Python:

![Final Source Code for Automating Facebook Login Using Python](https://cdn.hashnode.com/res/hashnode/image/upload/v1617042203454/63HLgWCip.png)

You can download the entire source code from my  [GitHub Repository](https://github.com/SaiAshish-Konchada/Automation-Code-Files/blob/main/Automatic_Facebook_Login.py). Be sure to star the repository, it contains a bunch of amazing automation code files.

And that's a wrap! We have successfully automated the login process of Facebook without the use of any bot and pure web scraping techniques. Using the process, I listed above you can automate any task on any website you wish for. The only things that are going to change are the values of attributes we will be targetting. 

What application would you like me to automate next? Should I build an Instagram Profile Picture Downloader, an Amazon Message Bomber or Whatsapp Automation? Let me know in the comment section below!

I'm dropping daily value bombs and development insights on [Twitter](https://twitter.com/InsightfulCoder). Make sure to follow me up. Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁