# cs50_labs
## Mario
### For the more comfortable 

### Program Overview

Click on Button below to get detailed information on where to code mario.c

{% spoiler Where To Code Mario %}

# Mario 

### Don't Code Mario In The Sandbox Environment

It is time to transition to coding in the IDE located at [https://cs50.io](https//:cs50.io)

In the IDE environment you will create your code and run it in a directory that you will create.
The path to the location will be ~workspace/unit1/mario

To setup the directoy do the following:

  * Open another browser window (shortcut command + n)
  * Navigate to [https://cs50.io](https://cs50.io) and login
  * cd to unit1 
  * `mkdir mario` and then cd into mario
  * create a new file called mario.c located in the mario directory
  * open mario.c in your IDE code editor window
  * With the Step by Step instructions open next your new window create your code
  * Remember in the IDE you need to save (shortcut: command + s ) your work before you compile it
  * Happy Coding!

{% endspoiler %}

{% video https://youtu.be/xX7DQGkEG48 %}

This 7ish minute video is the Walkthrough for this assignment. 
It covers the basics of what you need to know and do to complete it. 

{% next A Step-By-Step Guide %}

### Specification

* Write, in a file called mario.c in your ~/workspace/unit1/mario/ directory, a program that recreates these half-pyramids using hashes (#) for blocks.
* To make things more interesting, first prompt the user for the half-pyramid’s height, a non-negative integer no greater than 23. (The height of the half-pyramids pictured below happens to be 4, the width of each half-pyramid 4, with an a gap of size 2 separating them.)
* If the user fails to provide a non-negative integer no greater than 23, you should re-prompt for the same again.
* Then, generate (with the help of printf and one or more loops) the desired half-pyramid.
* Take care to left-align the bottom-left corner of the left-hand half-pyramid with the left-hand edge of your terminal window.

## World 1-1

Toward the beginning of World 1-1 in Nintendo's Super Mario Brothers, Mario must hop over adjacent pyramids of blocks, per the below.

![screenshot of Mario jumping up a right-aligned pyramid](pyramids.png)

Let's recreate those pyramids in C, albeit in text, using hashes (`#`) for bricks, a la the below. Each hash is a bit taller than it is wide, so the pyramids themselves are also be taller than they are wide.

```
   #  #
  ##  ##
 ###  ###
####  ####
```

The program we'll write will be called `mario`. And let's allow the user to decide just how tall the pyramids should be by first prompting them for a non-negative integer less than 24. 

Here's how the program might work if the user inputs `8` when prompted:

```
$ ./mario
Height: 8
       #  #
      ##  ##
     ###  ###
    ####  ####
   #####  #####
  ######  ######
 #######  #######
########  ########

```

Here's how the program might work if the user inputs `4` when prompted:

```
$ ./mario
Height: 4
   #  #
  ##  ##
 ###  ###
####  ####
```

Here's how the program might work if the user inputs `2` when prompted:

```
$ ./mario
Height: 2
 #  #
##  ##
```

And here's how the program might work if the user inputs `1` when prompted:

```
$ ./mario
Height: 1
#  #
```

If the user doesn't, in fact, input an integer between 0 and 23, inclusive, when prompted, the program should re-prompt the user until they cooperate:

```
$ ./mario
Height: -1
Height: 42
Height: 50
Height: 4
   #  #
  ##  ##
 ###  ###
####  ####
```
Notice that width of the "gap" between adjacent pyramids is equal to the width of two hashes, irrespective of the pyramids' heights.

Modify `mario.c` at right in such a way that it implements this program as described!

{% spoiler "Staff's Solution" %}

To try out the staff's implementation of this problem, execute by copying and pasting the entire path below into the terminal command line

```
~cs50/unit1/mario/less
```

{% endspoiler %}

### How to Test Your Code

Does your code work as prescribed when you input

* `-1` (or other negative numbers)?
* `0` through `23`?
* `24` or other positive numbers?
* letters or words?
* no input at all, when you only hit Enter?

{% next "Compile" %}

#### Compile your program
When you are done coding the above,  `compile` your program with the `make` command.

```
  $ make mario
```

##### DEBUG

You know now that you will almost certainly experience errors when compiling. 
Do your best to work through any them. Read the line number in the error and go to the code and see what you have created on that line.   It's always best to start with the **first** error that is reported. Sometimes fixing the first error fixes ALL of them. 

If the C compiler error messages are confusing to you, try using `help50`. This command is programmed by those smart Harvard folks
to generate more human readable debug and error messages. It can be helpful in pinpointing a problem. Use the command as shown below.

```csh
$ help50 make mario
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**mario**

To run the executable `isbn` file you will type the following at the terminal prompt
````
$ ./mario
````

{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/mario/more
```

#### Style

Check if you are stylistically correct by usng the 'style50' check below. This does *not* check for
syntax or other errors. It only checks if your code is inline with expected style requirements (spacing, indentations, etc...).

For Recommended Style Notes visit the following link [CS50 Style Guide](https://cs50.readthedocs.io/style/c/)

```
style50 mario.c
```

#### Submit

After you have checked your style and syntax above you are ready to submit your code.
You can submit your project directly from the command line as shown below.

```
submit50 cs50/2018/ap/mario/more
```

