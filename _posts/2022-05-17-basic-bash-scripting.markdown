---
layout: post
title:  "Basic Bash Scripting"
date:   2022-05-17 15:50:40
categories: security
---
*These are my notes on the Basic Bash Scripting segment of the Programming Basics section of the [Hopper's Roppers](https://www.roppers.org/) Computing Fundamentals course*

Bash has a built in scripting language. These days, you should just use Python for most things instead of writing Bash scripts, but you would be horrified if you knew how much of the internet, nay, how much of the world runs on bash scripts. Because bash and cron jobs (which we'll learn about later) are basically the underpinning of the modern world, you should probably get to know them.

**Bash Scripts:**
Open up your favorite text editor and build a file that looks like this and save it as "hello.sh". Note the top line which tells the shell what type of script it is, the file extension doesn't matter at all. (Note the two lines)

{% highlight shell%}
#!/bin/bash
echo "Hello World"
{% endhighlight %}

Then you can execute it using the command _$ bash hello.sh_. Similarly, you can use chmod to mark the file executable and then execute it using _$ ./hello.sh_.

As you might have noticed, the command you are running is exactly what you would run in a normal terminal command. Does that mean most of the knowledge you've learned remains applicable in here?

In a shocking turn of events, yes, it does. Don't get used to things working this nicely in the future.

**More Advanced Scripting**:

Check out what we can do to take input and execute commands in a script. Just build the script, save it as whatever you want, make it executable and run it. Don't worry about understanding it, I'm trying to demonstrate capability, not teach you how to do things at this point.
	
{% highlight shell%}
#!/bin/bash
echo "Enter Your Name"
read name
/# read is a nice little bash builtin function that isn't available in the shell,
/# but is in the scripting language. Also, lines starting with '#' are known as comments and aren't executed, these are in all languages, you'll get used to them. 
date="$(date)"
/# We just set the value that date returns to date
/# using something called "command substitution".
/# Unsurprisingly, you can do very complicated things with that.
echo "Welcome $name it is $date"
{% endhighlight %}

I saved this as *readName.sh* and ran it in the bash shell by writing _$ bash ./readName.sh_
In the shell it asked me to "Enter Your Name". I wrote Liz and it printed back "Welcome Liz it is Tue 17 May 2022 01:52:46 PM PDT".

Here is a program that counts to 10, printing out all the numbers as it goes.
Save it as counter.sh in your Documents directory and run it with *./counter.sh*.

{% highlight shell%}
#!/bin/bash
valid=true
count=1
while [ $valid ]
do
echo $count
if [ $count -eq 10 ];
then
break
fi
((count++))
done
{% endhighlight %}

So I navigated to my Documents directory in my bash shell and ran *chmod u+x counter.sh* on the file to give myself execute capabilities. I then ran *$./counter.sh* and it printed 1-10 on the screen.
Don't worry about what is going on in there, just know we can do whatever we want using bash scripting, though we probably should use something more modern like Python. Still, good to have in a pinch!

**Cron Jobs**:
Sometimes you might find yourself needing to run a command every couple of minutes, and luckily, there is a wonderful Linux tool for that named crontab.
	
These commands can be anything, from kicking off shell scripts, starting python processes, checking that programs are still running, really anything you want to **schedule**, cron jobs are the right way to do it.
	
A crontab file contains instructions for the cron daemon in the following simplified manner: "run this command at this time on this date".
	
Each user can define their own crontab file. Commands defined in any given crontab are executed under the user who owns that particular crontab.
	
To see what is in your crontab file, run: *crontab -l*
To edit it, run: *crontab -e*
(I was told "no crontab for octophetus" when I ran *crontab -l*)*
	
Using the *contab -e* command, add the following to the bottom of your cronjobs to execute the counter.sh script every minute:
{% highlight shell%}
*/1 * * * * /home/studentName/Documents/counter.sh
{% endhighlight %}

But what do we place in all those star holders for the time and date? (Note: remember the SPACE in between the stars and the beginning of our file location!)
	
Getting the proper date and time can be very tricky so don't learn it and just use existing examples on line. I use this site (<https://crontab.guru/examples.html>) for all my crontab-ing needs. (You better believe that Roppers run on crontabs and janky Python scripts).
	
On crontab guru we see an option for "every minute" as directed. They advise it is "* * * * *".
So let's go ahead and try:
{% highlight shell%}
/* * * * * /home/studentName/Documents/counter.sh
{% endhighlight %}

If you want to spend more time learning about Bash, check out <https://tryhackme.com/room/bashscripting> , but promise to come back!

Note: I couldn't tell if it was running or not since it runs in the background (even though it says echo). I edited the file on the line where it says *"echo $count"* to say *"echo $count >> /home/studentName/Documents/counterLog.txt"* and I saw it got created with "1-10" inside and each time it ran it appended to there.

**Assignment:**
**Questions**:
<ol>
<li>Write the bash script to append the date and time the script was run to a file named "dates.txt"
<li>Write the cron command to run the script you just wrote every Friday at noon.
</ol>

**Answers**:
<ol>
<li>
{% highlight shell%}
#!/bin/bash
date >> /home/studentName/Documents/dates.txt
{% endhighlight %}
<li>0 12 * * FRI /home/studentName/Documents/dateLog.sh
</ol>