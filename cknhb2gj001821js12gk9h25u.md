## A Beginners Guide to Bit Manipulation

Bit Manipulation or Bit Magic as it is popularly known as is a technique where we work directly on binary data or bits which results in faster code execution. If the concept seems to be frightening, don't worry. We will bust and understand everything with examples.

In this article, we'll explore:
```
1. Overview of Decimal and Binary Number System
   a. Conversion of Decimal number system  -> Binary Number System 
      Conversion of Binary number system  -> Decimal Number System
   b. Addition and Subtraction of Binary numbers:
2. Bitwise operators
3. Significance of these operations
    a. General Application
    b. Swapping
    c. Even and Odd
```
## 1. Overview of Decimal and Binary Number System

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618148409252/bQ1TZ7mjD.png)

The most common convention of writing numbers is the decimal number system. In this system, we write numbers in the power of 10.  For example,

(375)<sub>10</sub> = 3 x 10<sup>2</sup> + 7 x 10<sup>1</sup> + 5 x 10<sup>0</sup>

Similarly, computers are habituated to work on Binary numbers, corresponding to base 2.

(101)<sub>2</sub> = 1 x 2<sup>2</sup> + 0 x 2<sup>1</sup> + 1 x  2<sup>0</sup> = 5

### a. Conversion of Decimal number system  -> Binary Number System and vice versa

**i. Decimal number system  -> Binary Number System**

We convert decimal to binary by division as we are going from base 10 to base 2.

(10)<sub>10</sub> -> (?)<sub>2</sub>

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618391224873/a5Jw_0Pug.png)

The trick is to keep dividing the number by 2 and write the remainder beside it. 
- 10/2, remainder = 0
- 5/2, remainder = 1
- 2/2, remainder = 0

You've to write the binary bits in the bottom-up order along with 1 at the front. So, the binary representation of 10 will come as 1010.

**ii. Binary Number System -> Decimal number system **

We convert binary to decimal using multiplication as seen above.

(1010)<sub>2</sub> = 1 x 2<sup>3</sup> + 0 x 2<sup>2</sup> + 1 x  2<sup>1</sup> + 2<sup>0</sup> <br>
 = 8 +  0 + 2 + 0 <br>
 = 10

### b . Addition and Subtraction of Binary numbers:

![Addition and Subtraction of Binary numbers](https://cdn.hashnode.com/res/hashnode/image/upload/v1618393547478/_QyMnfZQY.png)

**i. Addition**

This is the truth table for addition of Binary digits.
<table>
  <tr>
    <th>Number 1</th>
    <th>Number 2</th>
    <th>Sum</th>
    <th>Carry</th>
  </tr>
  <tr>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
     </tr>
  <tr>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
   </tr>
  <tr>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    </tr>
  <tr>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
  </tr>
</table>

If we add,
- 0 + 0, we get the sum as 0 with no carry.
- 0 + 1, we get the sum as 1 and no carry.
- 1 + 0, we get the sum as 1 and no carry.
- 1 + 1, we get the sum as 0, and the carry as 1.

Let's say we want to perform addition as 5 + 6. The computer converts 5 and 6 from the decimal number system to the binary number system.

(5)<sub>10</sub> = (101)<sub>2</sub>
(6)<sub>10</sub> = (110)<sub>2</sub>

Adding the binary representation according to the truth table,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618388283288/JlHSMRFY1.png)

The highlighted 1 represents the carry bit. Convert 1011 to decimal, we get the result as 11, that is, in fact, 5 + 6. 

**ii.Subtraction**

**Spoiler alert:** There's nothing known as subtraction in the computer. The computer uses a method called 2's complement to perform subtraction using addition. So, if we want to perform 6 - 5, the computer treats it as  6 + (-5).

**Step 1:** Convert numbers from the decimal number system to the binary number system.

(6)<sub>10</sub> = (110)<sub>2</sub>
(5)<sub>10</sub> = (101)<sub>2</sub>

**Step 2:** Invert the bits of the number to be subtracted. (Change 0 to 1 and 1 to 0)

(5)<sub>10</sub> = (101)<sub>2</sub> = 010

**Step 3:** Add the numbers

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618390151602/AfLl4vTGP.png)

- If a carry is generated from the most significant bit(MSB)— the leftmost bit, that means the result is positive. Discard the carry it and add 1 to obtain the final answer. 
- If no carry is generated, that means the number is negative. In this case, you've to invert the bits of the answer.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618390268017/rdTqnlLet.png)

**Step 4:** Convert the answer obtained in binary back to the decimal number system.

(1)<sub>2</sub> = (1)<sub>10</sub>

Therefore, we get the answer as 1. 

## 2. Bitwise operators

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618148234602/dAx4VsuJI.png)

As we have Arithmetic operators to work on Decimal numbers, we have Bitwise Operators to work on Binary Numbers. The most commonly used Bitwise operators are:

- Bitwise AND(&)
- Bitwise OR(|)
- Bitwise XOR(^)
- Bitwise NOT(~)
- Right Shift(>>)
- Left Shift(<<)

<table>
  <tr>
    <th>Number 1</th>
    <th>Number 2</th>
    <th>AND(&)</th>
    <th>OR(|)</th>
    <th>XOR(^)</th>
  </tr>
  <tr>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
     </tr>
  <tr>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
  </tr>
  <tr>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
  </tr>
  <tr>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
  </tr>
</table>

Consider this as the master table. How to build this table? 

**1.  AND(&):** If both the bits of the numbers are 1, the output is 1 else 0.

**2. OR(|):** If both the bits of the numbers are 0, the output is 0 else 1.

**3. XOR(^):** If both the bits of the numbers are different, the output is 1 else 0.

Let's explore the other operators.

**4. NOT(~)** works on single bits. It inverts the value of the bits. If the input is 0 it converts it to 1 and vice versa,

**5. Right Shift(>>):** Shifts the position of bits to one place towards the right. The significance of the right bit is that it divides the number by 2. For example, let's say we have to right shift the number 12 two times.

**Problem:** 12>>2

**Solution:** 12 becomes 1100 in Binary <br>
Right shift bits once:  0110 <br>
Right shift bits twice: 0011 <br>

Hence 12 gets converted to 6 and then 3. 

**6. Left shift(<<):** Shifts the position of bits to one place towards the left. The significance of the left bit is that it multiplies the number by 2. For example, let's say we have to left-shift the number 12 two times.

**Problem:** 12<<2  

**Solution:** 12 becomes 1100 in Binary <br>
Right shift bits once: 11000 <br>
Right shift bits twice: 110000

Hence 12 gets converted to 24 and then 48. 

## 3. Significance of these operations

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618148583420/Ym0c-B-o5.png)

### a. General Application
  
Let's say you wanted to write a code where you are constantly multiplying/dividing the term by 2. 

```
for (int i = 1; i <= N;  i = i * 2)
{
   ------------------
   ------------------
} 
```

Instead of multiplication, you can directly use the left shift operator in the updation phase.

```
for(int i =1; i< = N; i =(i<<1))
{
   ------------------
   ------------------
}
```

### b. Swapping

You can perform swapping without the need for a third variable. The magic is created by the XOR operator.

``` 
int a = 5, b = 2;
a ^= b;
b ^= a;
a ^= b;
```

### c. Even/Odd 

What if I told you that we can completely eliminate the use of the modulo(%) operation to find out whether a number is even or odd. We can achieve this using **Bit Masking**. Before diving into Bit Masking, I would like to perform a small quiz. What is the pattern among these numbers?
 
2 = 10 <br>
4 = 100 <br>
6 = 110 <br>
8 = 1000 <br>
10= 1010 <br>

1 = 1 <br>
3 = 11 <br>
5 = 101 <br>
7 = 111 <br>
9 = 1001 <br>

If you notice correctly, you'd observe that the last digit of each even number is 0. Similarly for odd numbers, the last digit is 1. Therefore, to distinguish between even and odd numbers, we just need to figure out whether the last digit of a number is 0/1.
The concept is if we use AND any number with 1, we would receive the last digit of the number.

For example,

i.  8 & 1

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618147031022/9p1-uNQuy.png)

ii. 7 & 1

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618147063443/Lco3vliqn.png)

We can simply compare the result with 0 and verify if our number is even or odd. This process is called Bit Masking. We use 1 as a mask and perform an operation to get the desired output. 

Code snippet for Even and Odd numbers using Bit Manipulation technique:
```
int i = 8763;
if((i&1)==0)
System.out.println("Even Number");
else
System.out.println("Odd Number");
```
That's it for today, folks. In the next part of this series, we would discuss Bit Masking Techniques and move on to explore some advanced Bit Manipulation Techniques & Algorithms. 

This article was inspired by the  [DSA-One series](https://www.youtube.com/watch?v=N89PN_uyelU&list=PLUcsbZa0qzu3yNzzAxgvSgRobdUUJvz7p&t=0s)  by  [Anuj Kumar Sharma. ](https://www.linkedin.com/in/anuj-kumar-sharma-294533138/)

### Bonus Insights by  [The Insightful Coder](https://theinsightfulcoder.com/) :

-  Interested in Building Creative Beginner-Level Python Projects🐍?: Check out the  [Python Projects for Beginners Series](https://hashnode.com/series/python-projects-for-beginners-ckk31d9370h0vrus1blfl0a4y)😍

-  Interested in Building Your Own Artificial Intelligence Projects using Python?: Check out the [Python AI Series](https://hashnode.com/series/python-ai-series-ckkft33ux016dwjs11xlqbz4v)🧠

- I'm dropping useful developer resources, interactive quizzes, interviews tips and more on my  [Instagram](https://www.instagram.com/theinsightfulcoder/)  page 🖼

- Find and Download All My Project Source Codes at My [Github Repository](https://github.com/SaiAshish-Konchada) 🎁 
