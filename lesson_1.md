###Getting your computer ready
Activity: download and install python and pycharm (community edition)
Python can be found at https://www.python.org/downloads/
PyCharm can be found at https://download.jetbrains.com/python/pycharm-community-5.0.3.exe
Using the command line
Using Anaconda and iPython


###Why learn Python?
Python is a gateway language. It is a scripting language and is easy to install on any platform. It follows object‐oriented structures, meaning that you can apply its syntax and core constructs to other object‐oriented languages that you may be asked to learn (Java, C#, etc). Python is also the language of choice for many open‐source projects due to its ease of use and robust libraries, particularly in the security community. 

Difference betw 2.7 and 3.5
The End Of Life date (EOL, sunset date) for Python 2.7 has been set to 2020. This decision was made to clarify the status of Python 2.7 and relieve worries for those users who cannot yet migrate to Python 3. 

Python 2.7 is the last major release in the 2.x series, as the Python maintainers have shifted the focus of their new feature development efforts to the Python 3.x series. This means that while Python 2 continues to receive bug fixes, and to be updated to build correctly on new hardware and versions of supported operated systems, there will be no new full feature releases for the language or standard library.

However, while there is a large common subset between Python 2.7 and Python 3, and many of the changes involved in migrating to that common subset, or directly to Python 3, can be safely automated, some other changes (notably those associated with Unicode handling) may require careful consideration, and preferably robust automated regression test suites, to migrate effectively.

This means that Python 2.7 will remain in place for a long time, providing a stable and supported base platform for production systems that have not yet been ported to Python 3. The full expected lifecycle of the Python 2.7 series is detailed in PEP 373.


###Why learn web programming?
Simply put – most of the exploits we will try in Cybersecurity Fundamentals will require a working knowledge of web communications and protocols. The best way to learn how to exploit a website is to build one.

The Internet is Everywhere
As a Web developer, you’re going to have an impact. The Web has become ubiquitous, and your work will be used by people around the world as they hunt for information, conduct transactions of almost every sort, and communicate with friends, family, and business contacts through social media.

The Field is Expanding
The Web isn’t just about the Web anymore. When companies think about their websites today, they think about mobile technology and social media at the same time. The increasing use of smartphones, tablets, Internet TV, and even wearable technology needs to be taken into account by development teams when websites are designed and built. That’s expanding the reach of Web developers and the audiences they serve.

It’s Flexible
Web development has a lot of facets — the front end, the back end, the mobile Web, content management systems and e-commerce, to name just some. This gives professionals a range of paths to choose from as they go about planning their careers. For example, a PHP developer might focus on WordPress, while a front-end specialist develops expertise in Angular.

At the same time, new tools are making it easier to evolve your skills. By using Node.js, for instance, JavaScript developers can more easily apply their talents to back-end projects.

“This is really appealing work,” said Jake Spurlock, an engineer on Wired’s technical team, who sees Web development as being ideal for people who enjoy digging into details. “If you like solving problems, software development can be really rewarding.



###Ways to learn programming 
“Get the code on the page.”
-Quickly create programs by copying
-Experience working programs in a few minutes
-Little understanding of “why”
-Probably won’t pass a decent programming interview
-Harder time debugging



“Understand how the code and machine work.”
-Slower/ more methodical
-Working conceptual snippets in a few minutes
-Understanding of why/how and the ability to figure out how and why
-Probably will pass a decent programming interview
-Can troubleshoot/problems solve in a variety of tech situations
-Research universities teach this way


We'll try to do a little of both but because of time we will be much more focused on the former. That means that you'll be able to develop working programs during this course but unless you spend time on your own exploring, resesarching and attempting to understand what you have done you won't be able to create working programs of sufficient complexity on your own.
 
The first way is great for getting an overview and helping to determine if you're suited to programming without making sufficiently large investment. However, if you want to become a professional programmer it isn't going to cut it. 

###What is a scripting language
Traditionally, scripting may have referred to “incomplete” or “limited” languages. Usually used as the “glue” that tied different applications together, or just as an easy language to write something quick and dirty to automate some mundane task.

maybe 10 years ago JavaScript may have been considered a “limited” language – back when it was really mostly used to do some quick form validation or scroll some text on your browser, however that is no longer true today. This misunderstanding of JavaScript today is mostly accredited to developers that don’t understand it or have only used it to scroll text across a screen – and because it ends in “script”. Turn off JavaScript in your browser and try GMail, Facebook or even Google+. This is no longer an “incomplete” or “limited” language – in fact your web application would look incomplete without it; 1995 incomplete. Building a JavaScript based application today requires the same thinking and design you would give while building an application in C or Java. You need to apply the same design patterns that apply on the back-end. Speaking of the back-end, today you can even run JavaScript on the server side. So I can technically write a full GMail clone in just JavaScript.


Scripting languages are programming languages that don't require an explicit compilation step.

For example, in the normal case, you have to compile a C program before you can run it. But in the normal case, you don't have to compile a JavaScript program before you run it. So JavaScript is sometimes called a "scripting" language.

This line is getting more and more blurry since compilation can be so fast with modern hardware and modern compilation techniques. For instance, V8, the JavaScript engine in Google Chrome and used a lot outside of the browser as well, actually compiles the JavaScript code on the fly into machine code, rather than interpreting it. (In fact, V8's an optimizing two-phase compiler.)

Also note that whether a language is a "scripting" language or not can be more about the environment than the language. There's no reason you can't write a C interpreter and use it as a scripting language (and people have). There's also no reason you can't compile JavaScript to machine code and store that in an executable file (and people have). The language Ruby is a good example of this: The original implementation was entirely interpreted (a "scripting" language), but there are now multiple compilers for it.

Some examples of "scripting" languages (e.g., languages that are traditionally used without an explicit compilation step):

Lua
JavaScript
VBScript and VBA
Python
And a small smattering of ones traditionally used with an explicit compilation step:

C
C++
D
Java (but note that Java is compiled to bytecode, which is then interpreted and/or recompiled at runtime)



###What is object-oriented programming
what are variables - containers in memory for your program to use
how do you name variables
what are data types
what does it mean that python is not heavily typed
what are some types of variables in python 
what are strings
what is null/none
what is int/decimal
printing from python
comments in python - comments are for people
* write your first program
 - hello world
* add comments to your program 
getting input from the user
 - add your name to your program
when to use single quotes, double quotes and triple quotes
printing special characters - \n \t
* make a program using strings, tabe and newlines to print the lesson and topic table
len() getting the length of a string or list
indexing or slicing example
how does indexing work in python
creating a substring
making strings upper case and lower case
* make a program that prints hello, world from the following variables. You may only use these variables and the print command or indexing. You can't add any strings.
hello = "hello"
mandella_quote = "Education is the most powerful weapon which you can use to change the world."
formatting strings - pretty printing
doing math in string formatting
* exercise - print the phone number example from slide
finding stuff 
replacing stuff
stripping white space
* print the address and the length with and without the leading and trailing white space
counting() the number of times a substring exists
 *write a program to print the number of times the word three occurs in the following quote from Monty Python
"""And the Lord spake, saying, "First shalt thou take out the Holy Pin. Then shalt thou count to three, no more, no less. Three shall be the number thou shalt count, and the number of the counting shall be three. Four shalt thou not count, neither count thou two, excepting that thou then proceed to three. Five is right out. Once the number three, being the third number, be reached, then lobbest thou thy Holy Hand Grenade of Antioch towards thy foe, who, being naughty in My sight, shall snuff it.""

math is hard - so use python
floor division
modulo
other basic math: abs, exponents, sqrt, 
importing libraries - import math


boolean expressions
= vs ==
> < >= <= operators
conditionals - if only there was a way of controlling program flow
random numbers

projects:
happy birthday
bottles of beer
movie titles part 1 (doesn't use dictionaries or lists or save to file yet)