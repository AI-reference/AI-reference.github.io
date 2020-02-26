---
title: Programming
---

##### On this page I will give some basic programming skills and information.
##### If you want to try to code along, first take a look at the IDEs section in the [Tools](Tools.md) section.
___

* [Languages ](#languages)
* [Programming styles](#programming-styles)
* [Data types](#data-types)
* [If Else](#if-else)
* [Loops](#loops)
* [Functions / methods](#functions-and-methods)
* [Recursion ](#recursion)
* [Learn java](#learn-java)
* [Learn python](#learn-python)

___

#### Languages
There are many different programming languages, each with its own strengths and weaknesses. Some languages are used just to write scripts (a list of instructions to be executed automatically which could otherwise be ran by a human operator) and others to write massive software systems. In the AI bachelor you will learn to write code some of the most popular languages (and one of the most obscure too). 

Your will start writing code in [Java](#learn-java), a well-established classic among the programming languages; like the Coca-cola of programming languages. Java is about middle of the road in high- vs low-level programming. High level programming means you can express your ideas in less code - further away from machine code (all the way down it’s ones and zeros). Low level programming languages are more difficult to master. They are closer to machine code and can manipulate memory directly and even work with single bytes in your machine. Examples of low level programming languages are C and C++. You may write some C code in one or two elective courses if you’d like (e.g. Hacking in C). 

The other very prominent programming language you will use in AI is [Python](#learn-python). Python in the most popular programming language (recently surpassing Java). Python is a high-level programming language which was originally a scripting language but grew out to be a fully capable programming language. Python is great.

#### Programming styles
There are different styles of programming, each with their own use. Some of the styles you will learn in the bachelor: imperative programming (writing coded statements that change the state of your program), Object Oriented programming (defining your program in the context of objects of different classes with their own properties), functional programming (defining functions that behave the same every time you call them). I won’t go into depth into these different styles of programming, you learn these in your first programming courses. 

#### Data types
In programming, we work a lot with variables. Variables are names we can give to pieces of information so we can easily manipulate it. For example we can say `potato = 19 * grape`. Now we can use the variable `potato` to refer to the value `19 * grape`, where `grape` is another variable. 

These variables have a _type_. There are a number of predefined types we can use, but almost any programming language allows you to create your own data types as well. I will list some of the most used built-in data types in programming here.

* String - a string is just a piece of text, it is usually defined by "quotation marks".
* Character - often called a _char_ can contain a single character like 'a'.
* Integer - often called an _int_ is a whole number, like 1, 2, 6, -473, etc.
* Float - a float (sometimes called a double) can contain any real number, like 17.3456.
* Boolean - a boolean contains a binary value which can be either _true_ or _false_.

Depending on the programming language, you may have to tell the compiler (the program that transforms your code to machine-readable commands) what type a piece of information is at all times. In java for example, you always need to say what type of variable it is that your are making or using. A String variable in java is creates as follows:
```java
String name = "Jane Doe";
```
This is called _static typing_, you have to always say what type of data you are working with so the compiler doesn't get confused. Other languages that use static typing are C, C++, Scala, and more.

In other languages, for example Python, javascript and PHP, you do __not__ have to say what type of data your variable is. You can simple give the variable a name, and a value, and the compiler will figure out what it is by looking at the value. Example in python:
```python
name = "Jane doe"
```
This is called _dynamic typing_. 

Static typing allows the compiler to check for some obvious bugs before running the code, for example multipling a String by -3.67. These errors can be spotted by the editor while coding, which prevents you from having to debug your program from simple type errors. Dynamic typing is nice because it allows the programmer to write code quickly and change a variable however they want to. They do have to be more careful with writng their code to make sure all of it fits together nicely.

#### If Else
Often, we want some piece of code to run only if a condition is true, and maybe another piece if it isn't true. For example, if the variable `name` is equal to "Thijs", we can run a certain piece of code, and something else if this is not the case.

I will give an example in java:
```java
if(name.equals("Thijs")){
	System.out.println("This person is great!");
} else if(name.equals("")) {
	System.out.println("No name given.");
} else {
	System.out.println("I don't know this person");
}
```
In this piece of code we can see three sub-parts. First, if name is equal to "Thijs" we print one thing to the screen. If this is not the case, we can go to the next block, an else-if clause. This is checked only if the first if condition is not true. You can add as many else-ifs after this, and each will be checked if all the previous conditions are false. Finally, if the _if_ and optional _else if_ blocks are all false, we can include an _else_ block. This block of code is executed if none of the conditions given before are true.

Clearly, the condition in an if-statement must resolve to a boolean, since if must be either true or false. Comparisons resolve to a boolean, since the statement can be either true or false. We can concatenate multiple conditions with _and_ and _or_ operators. in the statement
```java
if(condition1 && condition2)
```
both conditions must be true to enter the block of code in this if clause. In the statement
```java
if(condition1 || condition2)
```
Only one of the conditions has to resolve to true.

#### Loops
To execute the same piece of code multiple times after each other, you don't have to copy this code x times. You can write a _loop_ which tells the computer for how many times, or for how long this code should be executed. We generally distinguish two different kind of loops, a for-loop and a while-loop. You can use either in any case, but sometimes one is more useful and clear than the other. A for-loop (in java) generally consists of three parts: initialization, stop condition, iteration step. Here is an example of a for-loop in java:
```java
for(int i = 0; i < 20; i++){
	// Do something
}
```
In the example, we define a for-loop with and integer named `i`, and set it to 0. In the condition part we say that this code should be ran until `i` is no longer smaller than 20. In the iteration part, we say that every time this piece of code is ran, we increase `i` by 1. `i++` is a short notation in java for `i = i+1`.

In while-loops, we only take this middle part of the for-loop, the condition.
```java
while(!isFinished()){
	// Do something
}
```
In the while-loop, the condition is once again a boolean (true or false), and the block of code keeps repeating until this condition is false. In the example, we continue running the code until the _function_ `isFinished` return True. The exclamation point is the negation operator, and it means to reverse the boolean that comes after it. `!true == false`. Functions will be discussed in the next section.

#### Functions and methods
A program consists of command you write from the computer to execute. A way to avoid having to write the same piece of code over and over again we can write a function (it's called a method if it belongs to a specific class). In a function we write the piece of code and by calling that function the computer runs that piece of code. A function can take _parameters_, which are pieces of data you can give your function which it can then manipulate. Here is an example of a function in java.
```java
public int numDivisors(int number){
	if(number < 1){
		return 0;
	}
	int count = 0;
	for(int divisor = 1; divisor <= number; divisor++){
		if(number % divisor == 0){
			count++;
		}
	}
	return count;
}
```
It computes the number of divisors of a number. Let's dissect this function piece by piece to see what everything does.

The keyword `public` states that this function is visible from everywhere in the java program, so we can always use it. `int` denotes that the function will return an integer, in this case the number of divisors. `numDivisors` is the name of the function; this can be anything but can only contain letters, numbers and underscores. It is customary in java to write function names in camelCaseLikeSo, capitalizing each word after the first. `(int number)` is the parameter of this function, when we _call_ this function, we have to give it an integer (namely the number for which we want to compute the number of divisors), and this integer will be called `number` inside of this function. Then inside the function we define the trivial case, simply that if a number is smaller than 1 it has no divisors (assumed for simplicity). So we check this with an if-statement. the keyword `return` exits the function and gives whatever comes after it, in this case it will stop the function and give back 0. For the other numbers we will have to start counting. We can create variables in a function, these are called _local variables_. These variables are only accessible from within this function. We create a variable `count` to store the number of divisors we find. Then we enter a loop of all numbers under (and equal to) `number`. For each of these number we check in `number` is divisible by the divisor by checking if there is no remainder when we divide them. If so, we increase `count` by one. At the end of the loop we return `count` as the number of divisors.

We can now use this function to compute the number of divisors of any number. We can do that by calling the function, and printing the result to the console like so.
```java
System.out.println(numDivisors(16));
System.out.println(numDivisors(1050));
System.out.println(numDivisors(6));
```

#### Recursion
Recursion is a useful programming tool, but can be quite tricky. Recursion is defined by calling a function in the body of that same function. This can lead to some very interesting behavior, but is also an easy source for tricky bugs. A recursive function should have some way to stop before calling the function again in its function body, otherwise it would call that function endlessly over and over again, crashing the program. This stopping criterion is called the base case. Let's first introduce an example.

<details>
<summary>Example in java</summary>
<p>

```java
public int factorial(int n){      
      if (n == 1)      
        return 1;      
      else      
        return(n * factorial(n-1));      
}  
```

</p>
</details>

<details>
<summary>Example in python</summary>
<p>

```python
def factorial(n):
	if n==1:
		return 1
	else:
		return n * factorial(n-1)
```

</p>
</details>


Given is the function for the mathematical expression factorial (n\*(n-1)\*...\*2\*1 = n!). The base case here is 1, since the factorial computation stops at 1. We also know that n! = n * (n-1)!

We use this definition to define a recursive function that computes the factorial of any given number. The else part of this function computes n * the output of this function with parameter n-1. this continues all the way down until we get to n=1. In this trivial case, 1! = 1, so we return 1. This returned value can now be used in the computation of the function that called it, which value can then be returned to again the function that called it, until we get to the first time we called the function. For `factorial(5)` we basically compute `5 * (4 * (3 * (2 * 1)))`. Often, the use of recursion can be substituted by a loop of some sort, but sometimes recursion really is the better choice.


#### Learn java
In this section I will provide links to basic java lessons. You will be taught java at the very start of the bachelor too. This section can also function as some extra resources if you don't understand a particular concept in java.

* [Quite long tutorial with java basics, including topics mentioned above](https://www.youtube.com/watch?v=eIrMbAQSU34) time-stamps for various topics are in the description.
* [A java tutorial playlist](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpPpdR_9IQBUDLjYalvdrGGb) with many useful videos, if you understand the concepts mentioned here on this page and in the tutorial above, you should focus on the videos from classes and objects on (video 26+).
* [Codecademy](https://www.codecademy.com/learn/learn-java). On this website you can learn to code java in an interactive way. It's really good to get the basics right.
* [Learn java online](https://www.learnjavaonline.org) is a free website where you can learn to write java code and run it in the browser, quite cool!
* Any concepts you learn in the first courses on programming you can find many good tutorials for on Youtube. Really do watch some Youtube videos if you don't understand a topic, they really really help.

#### Learn python
Here I will provide some links to learn python, the most popular programming language currently. You gradually code more and more in python as you advance in your bachelor since python has many great machine learning libraries and works really well with AI concepts.

* [Socratica python playlist](https://www.youtube.com/playlist?list=PLi01XoE8jYohWFPpC17Z-wWhPOSuh8Er-). Socratica is an amazing Youtube channel with loads of python videos, starting with installation and the basics. Lots of dry humor, and with an AI feel to it. It's fun.
* [Learn python](https://www.learnpython.org) is a website with free python coding tutorials, where you actually get to write and test code.
* [Numpy video](https://www.youtube.com/watch?v=QUT1VHiLmmI). One of the most used python libraries is Numpy. It contains code for all things numbers, and especially arrays. Try to learn this when doing your linear algebra course and try to find some python code to do the operations you learn there.
* [Codecademy](https://www.codecademy.com/learn/learn-python-3) also has a Python course, but sadly it's only available to pro accounts. If you do want to get serious with codecademy, you can consider it. It has many many great courses on loads of topics, concepts and programming languages. It's quite expensive though. I wouldn't buy a pro account if you are planning to do just one or two courses.




