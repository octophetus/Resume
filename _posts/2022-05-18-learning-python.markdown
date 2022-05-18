---
layout: post
title:  "Learning Python"
date:   2022-05-18 12:15:00
categories: web dev
---
*These are my notes on the Learning Python segment of the Programming Basics section of the [Hopper's Roppers](https://www.roppers.org/) Computing Fundamentals course*

Python is a programming language that has found incredible success, largely due to the fact that code written in it is readable and things just work. Programming is an exacting art, and Python doesn't force you to work very hard to understand why things are the way they are. No language is perfect. There are tradeoffs with all languages, some do better than others at various activities, some are worse. Python is the most straightforward language to write code and do things with, and has the best documentation examples for you to work off of. It is considered to be "slow", but when people tell you that, ignore them and continue writing your code.

If you want to learn C, and you should to get a deeper understanding of computing, check out my [rough roadmap](https://www.hoppersroppers.org/roadmap/training/c.html) once you have finished this course.


**What is Python?**

Python is a language developed primarily by Guido van Rossum, the affectionately named 'Benevolent Dictator for Life'. He began work on it in 1989 and since then thousands of people have contributed to the core code base, and even more have written modules and extensions to allow more to be done with the language.
	
Other aspects of the Python philosophy are:
<ul>
<li>Beautiful is better than ugly.</li>
<li>Explicit is better than implicit.</li>
<li>Simple is better than complex.</li>
<li>Complex is better than complicated.</li>
<li>Readability counts.</li>
</ul>
		
Overall, Python is often described using the words: High level, interpreted, dynamically typed, garbage collected, readable. For the assignment you'll define those. Don't worry about what dynamically typed means right now.


**Python - Hello World:**

For Python 3: Print("Hello World")

For Python 2: Print "Hello world"
	
Setting up environments is very time-consuming, no matter what it is, but you will have to do this for basically every language, and every version of each language, so you will have to get good at it.


**On Linux:**

Ensure the most up to date version of Python is installed on your Linux box. Check this by running the command "python" from the command line.

Note: I got the following: Command 'python' not found, did you mean: command 'python3' from deb python3. So I typed python3 and it opened up the Python >>> I looked it up and 'python' is used for Python 2 and 'pyton3' for Python 3. I am going to edit my .bashrc file to have Python 3 assigned to the 'python' command:

*alias python='python3'*
	
If it responds with Python2 or the program is not installed, install a modern Python version with <https://docs.python.org/3/using/unix.html#on-linux>


**Command Line Interpreter:**

When you run python from the command line it brings up something called an interpreter >>> . The Python interpreter is neat because you can use it to run programs one at a time.
	
With the interpreter open, do some basic math:
{% highlight python %}
a = 2
b = 3
c = a + b
Print(c)
{% endhighlight %}

		
That should have printed c, which would have displayed as 5.
	
You can also print text from the interpreter. A program that prints "Hello World!" to the screen is the classic first thing most tutorials teach. Far be it from me to break with tradition, so here goes!

{% highlight python %}
print("Hello World")
{% endhighlight %}

Make sure to have the quotes around the words that you printed. Don't worry about what is happening right now, this is just to show what is possible. To close out the interpreter, type exit().


**Python Programs:**

We used the interpreter above, but you can only do very basic programs from the interpreter, so usually you run python programs as their own files.
	
Python makes this incredibly easy in comparison to many other languages.
	
Here is the code we will use inside our program:
{% highlight python %}
print("Hello World!")
{% endhighlight %}

You might notice that as the same thing that the interpreter took as input. Save it as "helloworld.py". ".py" is the python file extension. It is just a text file, but the ".py" tells the OS what to do with the file if you try to execute it.
	
Then, from the terminal, run that file you just created with typing:
{% highlight shell%}
$ python helloworld.py
{% endhighlight %}
		
Congratulations! Now you know how to program in Python! It definitely won't get any more difficult than that!


**High level:** A high-level programming language is a programming language with strong abstraction from the details of the computer. You can think of the high level referring to a high level of abstraction away from the nuts and bolts. This is as opposed to a low level language like assembly (one step above binary) which is not very human readable at all.

**Interpreted:** An interpreted program is interpreted as opposed to compiled. I think it is generally easier to explain both.

**A compiled program** has to be modified into machine code (compiled) before it is used. The binary is then permanently stored. As an analogy, think of a novel that was written in one language and then translated into another. For example, the Harry Potter novels were written in British English, and were then subsequently translated into 67 other languages, including Hindi, Latvian, and Latin. In much the same way, a computer program can be compiled (or "translated") into machine code, and it may potentially be compiled into different architectures (or "dialects") of machine code to suit different computers. Each translation will be a unique version of the program, in the same way that each translated book is a unique version of the original novel. To take the analogy further, if I was fortunate enough to have written the first Harry Potter novel, it may be the case that I wouldn't understand the language into which it is translated.

**An interpreted program** is stored in a human-readable form. When the program is executed, an interpreter modifies the human-readable content as it is run. This is more analogous to the role that a human interpreter performs. For example, rather than translating the British English version of Harry Potter into Latvian and then providing the Latvian version to someone who understands the language, (as per compilation), we could hire a translator who knows both British English and Latvian. The translator may choose to read each line from the British English novel, translate each line (one at a time) into Latvian, and, as each line is translated, relate it to the listener.

**Which is best?** There are advantages for both types of software development. As a generalization, compiled programs are faster to run but slower to develop. Compiled programs often run faster because the computer only needs to execute the previously translated instructions. In interpreted languages, every time the program is run the computer also needs to translate each of the instructions. This translation causes a delay, slowing the execution of the program. On the other hand, interpreted languages are often written in a smaller time frame, because the languages are simpler and the whole program does not need to be compiled each time a new feature is bug tested.


**Dynamically vs. statically typed:**

**Statically typed languages:**

A language is statically typed if the type of a variable is known at compile time. For some languages this means that you as the programmer must specify what type each variable is (as in, specify that a variable is an integer or a string, etc.). For example int a can only take an integer type at runtime.

The main advantage here is that all kinds of checking can be done by the compiler, and therefore a lot of trivial bugs are caught at a very early stage.

Examples: C, C++, Java, Rust, Go, Scala


**Dynamically typed languages**

A language is dynamically typed if the type is associated with run-time values, and not named variables/fields/etc. This means that you as a programmer can write a little quicker because you do not have to specify types every time. For example var a can take any kind of value at runtime. This might create an issue when someone writes "43535" as their name, or "Liz" as their age and you try to utilize that data in unexpected ways.

Examples: Perl, Ruby, Python, PHP, JavaScript, Erlang


**Garbage collected:**

Garbage collection (GC) is collecting or gaining memory back which has been allocated to objects but which is not currently in use in any part of our program. A more detailed answer is that garbage collection is the process in which programs try to free up memory space that is no longer used by objects.

Garbage collection is implemented differently for every language. Most high-level programming languages (like Python) have some sort of garbage collection built in. Low-level programming languages may add garbage collection through libraries. If you write a quick little program in C, you don't really need to worry about memory collection. But you can imagine in a memory hog of a project, that you might want to free it up. Long story short, in C it is done manually and if you don't do it correctly, you can suffer from memory leaks and crashes.

Garbage collection is a tool that saves time for programmers. For example it replaces the need for functions such as malloc() and free() which are found in C. It can also help in preventing memory leaks.

The downside of garbage collection is that it has a negative impact on performance so if you are running a close to the metal program like C, you don't want to waste time and bloat.


**Readable:**

Readability means how easy the computer program is to understand for a human. Computer program readability is slightly equivalent to readability in literacy. One of the things that has made Python successful is its readability. The code is clear and easy to understand. One of the reasons for this is that Python uses words for a few things that other languages use symbols for. Of course the C language or any other language is readable by people who are skilled at it, it's not binary after all. But some languages are easier to read (and understand what is going on) than others

For a quick illustration, compare our hello world program in Python vs. Java:

**Python:**
{% highlight Python %}
Print("Hello World!")
{% endhighlight %}
	
**Java:**
{% highlight java %}
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); 
    }
}
{% endhighlight %}

As I said, of course someone who is versed in Java can of course parse this, but you can image how chaotic something starts to feel the more intricate the program becomes. This is probably why a lot of beginners feel Python is a relatively easy language to learn, because so much of it makes sense to the eye before you've actually learned it. 


**Resources for learning Python:**
	
**Codecademy Python 2** (it is free and not a LOT has changed for Python 3) - <https://www.codecademy.com/learn/learn-python>

**PythonTutor Visualization** - While you are working through this, use the amazing PythonTutor Visualization anytime you are trying to understand what is going on behind the scene with your code. It's super helpful and will help you understand debugging in a visual manner. <http://www.pythontutor.com/visualize.html#mode=edit>

**Automate the Boring Stuff** - If you want to get good at programming, you should go and complete all the exercises in Automate the Boring Stuff (<https://automatetheboringstuff.com/>) in Python 3. Once you have done that you will be capable of just about any scripting task in Python if you have the time to do your research and work through it.

For now, I just want you to work through Chapters 9-12 of the Automate the Boring Stuff curriculum. We skip the first few chapters, but you generally have learned them from CodeAcademy already. If you're having trouble with Chapter 9 (you probably will), step back a few chapters and work through them until you feel comfortable moving forward.


**Projects Worth Doing** - <https://www.hoppersroppers.org/library/interestingProjects.html>


**Teach Yourself Computer Science** - If you want to learn Computer Science properly, I recommend you work through <https://github.com/ossu/computer-science/blob/master/README.md>. It's a fairly comprehensive education.

This is outside of the scope of this course, so I'd prefer if you stuck around, but the entire point of learning is following what you are interested in. No hard feelings if you go, just promise to come back!

Recommend you start at this course, as you already have some python experience. <https://github.com/ossu/computer-science/blob/master/README.md#introduction-to-programming>


**Programming is something that takes a lifetime to get good at, so don't worry about being good at it for a while. Focus on making things that work just well enough to get the job done.**


