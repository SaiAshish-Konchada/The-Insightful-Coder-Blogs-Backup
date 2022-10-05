## Demystifying Time Complexity & Big O Notation

One of the most important concepts in software development is analysing the time complexity of an algorithm. In technical interviews, you'd often find interviewers asking, "What's the time complexity of this algorithm?" or "Can you improve the time complexity?" If you've no idea what time complexity means or what the fuss about Big O is all about, stick till the end to find out!

## What is Time Complexity?

![Time Complexity](https://cdn.hashnode.com/res/hashnode/image/upload/v1618086630981/i1Xrzpbef.png)

Time complexity is the **time taken** by an algorithm as a **function of the length of the input**. In short, it tells the running time or **performance** of a program as the size of the input is varied.

## Why do we need to understand Time Complexity?

![Understanding Time Complexity](https://cdn.hashnode.com/res/hashnode/image/upload/v1618085877205/GCNqIjS2y.png)
Time complexity helps us to determines the **scalability** of an algorithm. Suppose, you're at a party and you want to use an Instagram filter to capture the joyous occasion. Alas, the filter takes years to load. Your smiles turn into a frown as your mood gets ruined. So much for a party, huh?

As a developer, it is necessary to understand which is the most efficient and optimised method to use in an application. 

## How to compare the time complexity of an algorithm?

![Compare time complexity of algorithm](https://cdn.hashnode.com/res/hashnode/image/upload/v1618085987351/2UtWwoe7H.png)
Let us take an example to understand this problem. Ali and Jack were given a task to write a program to find the sum of *n* numbers. Jack is a very hardworking guy who has mastered the fundamentals of a programming language. He doesn't pay attention to anything except programming. Here's how he coded the program:

```
int n=10, sum = 0;
for(int i=1; i<=n; i++)
{
     sum = sum + i;
}
System.out.println(sum);
```
Ali was smart. He focused on every subject in school and solved problems in a jiffy. When Ali was granted the same problem, he chuckled and used Mathematics to his aid. Here's  how Ali built his program:

```
int n=10;
System.out.println((n*(n+1))/2);
```
As you see from the above scenario, Ali was much more efficient as he avoided the shackles of using a loop to calculate his answer. If the size of the input increases, Jack's program will start to freeze and eventually int will overflow to present the wrong answer. Ali's magical line saves time and gives the right answer even for larger numbers.

## What is Big O?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1618084695849/cgaFO-C_x.png)

Image Source: [BigOCheatSheet](https://www.bigocheatsheet.com/)

Based on logic, we have understood time complexity and its comparison but we need something very distinct to compare the performance of different algorithms. If we start comparing the different type of sorting techniques by logic, it would get real tedious for our brain to execute the complexity of our problem. To optimise this, there's a superhero called the Big O.

As per  [Wikipedia](https://en.wikipedia.org/wiki/Big_O_notation), Big O or asymptotic notation is a **mathematical function** that describes the **limiting behaviour** of a function when the argument tends towards a particular value or infinity.

Big O basically tells us the **time complexity in mathematical terms** which can be easily compared. Our superhero Big O comes in different forms and sizes. I'll introduce you to them, right away!

## Understanding O(1)

O(n) stands for ** constant time complexity**. O(1) represents that no matter the size of the input, it takes the same amount of time to execute. For example,

```
int b = {1,2,3,4,5}
System.out.println(b[0]);
```
No matter the length of the array, the program will require one unit, constant time.
## Understanding O(n)

O(n) stands for** linear time complexity**. Linear represents the time takes by the algorithm is directly proportional to the size of the input. One of the most famous examples is the Linear Search algorithm. In linear search, we iterate over each element of the loop until we find a match. In the best-case scenario, the element could be present in the first position itself, thus effectively reducing the time complexity to O(1) as seen above. On the other hand, if the element is present at the end of the array or not at all, the loop has to iterate over all the elements in the array. Hence, the time complexity increases to O(n).

```
int a = 0, n[] = {1,2,3,4,5};
for(int i = 0; i <n.length; i++)
{
     if(n[i]==a)
     {
          System.out.println("Found");
          break;
     }
}
```
**Note:** If there are two for loops in a program, the effective time complexity is still considered as O(n) and not O(2n). We typically ignore the constants in front of the variables in such cases, because they both still represent a linear function.

## Understanding O(logn)

O(logn) also known as** logarithmic time complexity** denotes the time taken by the program to execute is proportional to the logarithm of the size of the input. The most famous example of this is the Binary Search algorithm. Let's suppose the worst-case scenario in the Binary search algorithm. We keep on halving our search array until we find the element or realise it is not present. In an array of 8 elements it will take maximum of 3 iterations(log<sub>2</sub>8) to execute. If there are 1 million elements, it'll take just 19 iterations. This makes Binary Search so much more powerful than Linear Search.

```
int arr[] = {10,20,30,40,50}; 
int l = 0, r = arr.length - 1;
while (l <= r) {
      int m = l + (r - l) / 2;
      if (arr[m] == x)
          return m;
      if (arr[m] < x)
           l = m + 1;
      else
           r = m - 1;
```

## Understanding O(n<sup>2</sup>)

O(n<sup>2</sup>) is also known as **Quadratic time complexity**. It represents that input is proportional to the square of the size of the input. It is most commonly seen in Bubble sort, Insertion sort and Patterns. Nested loops are an easy way to identify the O(n<sup>2</sup>) complexity. 

As the number of nested loops increases so does the power.

```
for(int i = 1; i<=5; i++)
{
     for(int j = 1; j<=i; j++)
     {
         System.out.print(j);
     }
System.out.println();
}
```
**Note:** If there are instances of multiple nested loops of different orders only the highest power will contribute to time complexity. For example, if T(n) = 3n<sup>3</sup> + 2n<sup>2</sup>+n. The time complexity will be Cubic, O(n<sup>3</sup>).

## Understanding O(2<sup>n</sup>)

O(2<sup>n</sup>) represents the **exponential function**. It is opposite to the logarithmic function. This mostly occurs in the case of Recursive functions, like recursive calculation of Fibonacci numbers. Another famous example of this complexity is the Hanoi Tower Problem. 

```
void solve_hanoi(int N, string from_peg, string to_peg, string spare_peg)
{
    if (N<1) {
        return;
    }
    if (N>1) {
        solve_hanoi(N-1, from_peg, spare_peg, to_peg);
    }
    print "move from " + from_peg + " to " + to_peg;
    if (N>1) {
        solve_hanoi(N-1, spare_peg, to_peg, from_peg);
    }
}
```
Program Source: [Stack Overflow](https://stackoverflow.com/questions/34915869/example-of-big-o-of-2n)
 
## Understanding O(n!)

O(n!) represents that the time complexity is the function of n **factorial. **This is the costliest it can get. One of the most classic examples is the Travelling Salesman Problem. Another example of O(n!) is given below:

```
const nFacRuntimeFunc = (n) => {
  for(let i=0; i<n; i++) {
    nFacRuntimeFunc(n-1);
  }
}
``` 

You should at all costs **avoid** the O(n!) complexity. 

## Let's Recap:

- **O(1)** - Constant time complexity (Best🎯)
- **O(n)** - Linear time complexity
- **O(log n)** - Logarithmic time complexity
- **O(n<sup>2</sup>)** - Quadratic time complexity
- **O(2<sup>n</sup>)** - Exponential time complexity
- **O(n!)** - Factorial time complexity (Worst😭)

## Valuable Resource:  [Big O Cheatsheet](https://www.bigocheatsheet.com/) 

Our superhero deserves a website of his own. I stumbled upon this website called the  [BigOCheatSheet.com](https://www.bigocheatsheet.com/) made by [Eric](https://twitter.com/ericdrowell). It contains an amazing comparison of the time complexity for different data structures and array sorting elements.

![Time Complexity of common data structures](https://cdn.hashnode.com/res/hashnode/image/upload/v1618084611822/5039Vbory.png)

![Time Complexity of various sorting algorithms](https://cdn.hashnode.com/res/hashnode/image/upload/v1618084629307/BR6c2vUa8.png)

In today's world, people are learning various frameworks, libraries & technologies without learning time complexity or Data Structures & Algorithms(DSA). If you ask any developer working in the top MNC's, they'll advise you to master the fundamentals and learn DSA as it greatly helps in problem-solving and writing efficient code. With that said, I hope our superhero continues to be our guardian angel forever. Cheers🍻