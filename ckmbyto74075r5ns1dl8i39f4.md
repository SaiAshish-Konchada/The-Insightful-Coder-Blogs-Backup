## How to Build an URL Shortener & Expander Using Python

Welcome to the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y) 🙋🏻‍♂️

I'm  [Sai Ashish](https://www.linkedin.com/in/sai-ashish/) and today, I'm going to show you how to build an URL Shortener & Expander using Python😍

How cool is that? Let's get started 🚀

## What are we going to learn today?

```
1. What is a URL?
2. Understanding the URL structure
3. Why do we shorten or expand an URL?
4. Basics of Python: Conditional Statements, Type Casting, Functions
5. The Pyshorteners module
6. Implementation of the URL Shortener & Expander with detailed explanation
```
## 1. What is a URL? 

![What is a URL? ](https://cdn.hashnode.com/res/hashnode/image/upload/v1612002587678/0L2BkoqzP.png)
A Uniform Resource Locator(URL) is a web address which specifies the location of a particular file on the internet. That particular file could be the HTML webpage itself or the CSS style sheet, images, video embeds etc.

## 2. Understanding the URL Structure

![Understanding/ What is the URL Structure](https://cdn.hashnode.com/res/hashnode/image/upload/v1615895528506/lzM1TDWS6.png)
Typically a URL has 5 parts:

**1. The Scheme** <br>
The Scheme tells the web servers which protocol to use while accessing a page on a website. The most common examples are http and https, while there are quite a few other such as ftp and mailto. The Insightful Coder uses the https: protocol, indicating the  [Hyper Text Transfer Protocol](https://developer.mozilla.org/en-US/docs/Web/HTTP)  with a  [Secure Sockets layer](https://www.ssl.com/faqs/faq-what-is-ssl/) . 

**2. The Subdomain** <br>
The Subdomain is an additional part to the domain name. For example, blog, shop or offers provides the website’s blog, shop or offers page.  It is used to indicate that a website has more than one part apart from the main page. At The Insightful Coder, we only have the second-level domain.

**3. The Second-level domain**<br>
The Second-level domain is the name of the website. theinsightfulcoder is the second-level domain of our website.

**4. The Top-level domain**<br>
The Top-level domain or TLD specifies the entity a website gets registered on the internet. The most commonly used TLD are .com, .org, .net, .dev, .in etc. As you can see, The Insightful Coder has a TLD of .com

**5. The Subdirectory**<br>
The Subdirectory specifies the page you're currently on. For eg, for this article the subdirectory is ```/create-your-very-own-url-shortener-and-expander-using-python```

## 3. Why do we shorten or expand a URL?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615895761774/0WYL1OkcQ.png)
### a. URL Shortener:
A URL shortener is a tool to shorten a URL. 

Which URL would you rather prefer ```http://somerandomkeywords.randomdomainname.tld/unecessary-long-post-slug-uggh!``` or ```https://theinsightfulcoder.com``` ?

**We use URL shortening for: **

- **Beautification:** A shortened URL is a beautiful URL. A shortened URL looks neat and clean, easy to understand and hence, can generate more traffic to your website.

- **Easy to remember:** A short URL is easier to remember than a long one. 

- **Word of Mouth Communication:** Suppose you want to share the name of your website to a friend, a colleague or a recruiter. Or you want to print the name of your website on a card or display it during a presentation or video conference. Which URL would you choose?  With a shorter URL you can leverage the word of mouth communication. 

- **Social media marketing:** Social Media such as Instagram or Twitter provide a strict number of characters or links you can use to showcase your URL. A shorter URL gives the users the chance to focus on what's important.

- **More Clicks = More Traffic = Better page visibility:** URL Shortening becomes a major factor to get clicks website. More clicks = More traffic = Better page visibility. 

### b. URL Expander

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615895833498/Dsq3r64N9.png)
A URL expander is a tool used to expand a URL.

**We use URL expanding for: **

While shortening a URL has many benefits, spammers and hackers have found a convenient way to redirect a shortened URL to a spammy or malicious website. To be aware of such malpractices and which website you're visiting, it is a good practice to check where the shortened URL points at.

## Time to Code:
 
![Time to Code by The Insightful Coder](https://cdn.hashnode.com/res/hashnode/image/upload/v1611771833314/Uugrd3XOg.jpeg)

You can access the exclusive theory for this build  [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/URL%20Shortener%20&%20Expander)📄

For this build, we would be using the pyshorteners module. As per the official  [documentation](https://pyshorteners.readthedocs.io/en/latest/) , Pyshorteners is a Python lib to help you short and expand urls using the most famous URL Shorteners availables.

The Pyshorteners module provides a variety of different services to choose from. Some of them are Adf.ly, Bit.ly, Cutt.ly, Git.io, Po.st, Short.cm, Tiny.cc, TinyURL.com, Tiny.cc.

To install the pyshorteners module, run the following command in the terminal:

```
pip install pyshorteners
```

For our build, we will be using tinyurl but you are free to choose any service you like to.

The first step is to import Shorteners from the pyshorteners module. We implement it as:

```
#importing the required library
from pyshorteners import Shortener
```

Let's store an instance of the shortener in a variable. 

```
s = Shortener()
```

Now, we can just use ```s``` to access the functionalities of Shortener().

Next, we want to ask the user if he wants to expand a URL or shorten it.

```
choice = int(input("Enter 1 for link shortener and 2 for link expander: "))
```

Let's define a function, ```short()``` to execute link shortener.

```
def short():
```

Next, we want the link to be shortened.

```
link = input("Enter the link to be shortened: ")
```

Pass this link to tinyurl's short function. 

```
shortened_link = s.tinyurl.short(link)
```

Let's give our users the short link.

```
print(" The Shortened Link is: " + shortened_link)
```

Similarly, let's define a function for link expander. The only difference being, instead of using short(), use the expand() function.

```
def expand():
       link = input("Enter the link to be expanded: ")
       expanded_link = s.tinyurl.expand(link)
       print("The Expanded link is: " + expanded_link)
```

If the user chose 1, we call the ```short()``` function, the ```expand()``` function if 2 and an error message for any other input.

```
if choice == 1:
    short()
elif choice == 2:
    expand()
else:
    print("Wrong Entry. Please try again.")
```
The Final Source Code is given below:

![The Final Source Code for URL Shortener and Expander](https://cdn.hashnode.com/res/hashnode/image/upload/v1612000123783/I4whpt5DZ.png)

**Code in Action 💪🏻:**

![URL Shortener using python](https://cdn.hashnode.com/res/hashnode/image/upload/v1612000134692/AgIc5Hwla.png)

![URL Expander using python](https://cdn.hashnode.com/res/hashnode/image/upload/v1612000159805/M9rmG6vbf.png)

We did it 🥳 We have made our own URL Shortener & Expander using Python! How amazing is that? As a gift for staying till now, you get access to my [Python For Beginners Series Repository](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners)  😍 This repository contains all the source code you'd need to get started as a Python Developer 🐍.

You can also download the source code to this project [here](https://github.com/SaiAshish-Konchada/Python-Projects-for-Beginners/tree/main/URL%20Shortener%20%26%20Expander). Do hit the twinkle star, if this article provided value to you 🔥

And while you're at it, consider giving this blog the maximum love you can and I promise to give you such value bombs every week 💣 Until then, take care 🙋🏻‍♂️

## Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- Wanna Discover Some Valuable Tech-Hacks 🛠?: Check out the [Tech-Hacks for Everybody Series](https://hashnode.com/series/tech-hacks-for-everybody-ckk3juqc10ihoqps16q0geabj)😎

- I'm also dropping daily value bombs and development insights on my  [Instagram](https://www.instagram.com/theinsightfulcoder/) Page. Make sure to follow me up 💯

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada)  🎁