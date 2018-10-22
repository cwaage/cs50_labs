# cs50_labs
## Mario
### For the less comfortable 

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

To prepare for the assignment watch the 7:44 minute walkthrough video below.
It covers the basics of what you need to know and do to complete it. 
Then use the Step-By-Step guide to work through the code. 

{% video https://www.youtube.com/watch?v=EGWRG5e1O2s %}

{% next A Step-By-Step Guide %}

### Specification

* Write, in a file called mario.c in your ~/workspace/unit1/mario/ directory, a program that recreates this half-pyramid using hashes (#) for blocks.
* To make things more interesting, first prompt the user for the half-pyramid’s height, a non-negative integer no greater than 23. (The height of the half-pyramid pictured in image below happens to be 8.)
* If the user fails to provide a non-negative integer no greater than 23, you should re-prompt for the same again.
* Then, generate (with the help of printf and one or more loops) the desired half-pyramid.
* Take care to align the bottom-left corner of your half-pyramid with the left-hand edge of your terminal window.

## World 1-1

Toward the end of World 1-1 in Nintendo's Super Mario Brothers, Mario must ascend right-aligned pyramid of blocks, a la the below.

![screenshot of Mario jumping up a right-aligned pyramid](half_pyramid.png)

Let's recreate that pyramid in C, albeit in text, using hashes (`#`) for bricks, a la the below. Each hash is a bit taller than it is wide, so the pyramid itself is also be taller than it is wide.

```
       ##
      ###
     ####
    #####
   ######
  #######
 ########
#########
```

The program we'll write will be called `mario`. And let's allow the user to decide just how tall the pyramid should be by first prompting them for an integer between 0 and 23, inclusive. 

Here's how the program might work if the user inputs `8` when prompted:

```
$ ./mario
Height: 8
       ##
      ###
     ####
    #####
   ######
  #######
 ########
#########
```

Here's how the program might work if the user inputs `4` when prompted:

```
$ ./mario
Height: 4
   ##
  ###
 ####
#####
```

Here's how the program might work if the user inputs `2` when prompted:

```
$ ./mario
Height: 2
 ##
###
```

And here's how the program might work if the user inputs `1` when prompted:

```
$ ./mario
Height: 1
##
```

And here's how the program might work if the user inputs `0` when prompted:

```
$ ./mario
Height: 0
```


If the user doesn't, in fact, input an integer between 0 and 23, inclusive, when prompted, the program should re-prompt the user until they cooperate:

```
$ ./mario
Height: -1
Height: 42
Height: 50
Height: 4
   ##
  ###
 ####
#####
```

{% spoiler "Try It" %}

To try out the staff's implementation of this problem, execute by copying and pasting
the entire path below (including the tilde `~` into the terminal command line 

```
~cs50/unit1/mario/less
```

{% endspoiler %}

## Pseudocode

**Don't Skip this step!**

I know you want to get some code into the editor, but this step really can help you focus on creating an algorithm that will convert into working code. 

First, on a piece of paper write some pseudocode that implements this program, even if not (yet!) sure how to write it in code. There's no one right way to write pseudocode, but short English sentences suffice. Odds are your pseudocode will use (or imply using!) one or more functions, conditions, Boolean expressions, loops, and/or variables.

{% spoiler %}

There's more than one way to do this, so here's just one.

1. Prompt user for height
1. If height is less than 0 or greater than 23 (or not an integer at all), go back one step
1. Iterate from 0 through height-1 (using `zero indexing`):
    1. On iteration *i*, print *i+2* hashes and then a newline

It's okay to edit your own after seeing this pseudocode here.

{% endspoiler %}

{% next %}

## Prompting for Input

Whatever your pseudocode, let's first write **only** the C code that prompts (and re-prompts, as needed) the user for input. 

Specifically, modify `mario.c` in such a way that it prompts the user for the pyramid's height, storing their input in a variable, re-prompting the user again and again as needed if their input is not a non-negative integer less than 24. Then, simply print the value of that variable, thereby confirming (for yourself) that you've indeed stored the user's input successfully, a la the below.

```
$ ./mario
Height: -1
Height: 42
Height: 50
Height: 4
Stored: 4
```

{% spoiler "Hints" %}

* Recall that you can compile your program with `make`.
* Recall that you can print an `int` with `printf` using `%i`.
* Recall that you can get an integer from the user with `get_int`.
* Recall that `get_int` is declared in `cs50.h`.

{% endspoiler %}

### Before you proceed, compile and run your code to be sure it accepts only valid user input. 

`compile` your program with the `make` command

```
  $ make mario
```
Run your exectuable file as below

```
./mario
```


## Building the Opposite

Now that your program is (hopefully!) accepting input as prescribed, it's time for another step.

It turns out it's a bit easier to build a left-aligned pyramid than right-, a la the below.

```
##
###
####
#####
######
#######
########
```
So let's build a left-aligned pyramid first and then, once that's working, right-align it instead!

Modify `mario.c` in the IDE such that it no longer simply prints the user's input but instead prints a left-aligned pyramid of that height.

{% spoiler "Hints" %}

* Keep in mind that a hash is just a character like any other, so you can print it with `printf`.
* You can actually "nest" loops, iterating with one variable (e.g., `i`) in the "outer" loop and another (e.g., `j`) in the "inner" loop. For instance, here's how you might print a square of height and width `n`, below. Of course, it's not a square that you want to print.

    ```
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++)
        {
            printf("#");
        }
        printf("\n");
    }
    ```
Example output where `n = 2`

      ```
      ##
      ##
      ```

Example output where `n = 5`

      ```
      #####
      #####
      #####
      #####
      #####
      ```

{% endspoiler %}

{% next %}

## Right-Aligning with Dots

Let's now right-align that pyramid by pushing its hashes to the right by prefixing them with dots (i.e., periods), a la the below.

```
.......##
......###
.....####
....#####
...######
..#######
.########
#########
```

Modify `mario.c` in such a way that it does exactly that!

{% spoiler "Hint" %}

Notice how the number of dots needed on each line is "inversely proportional" to the number of that line's hashes. For a pyramid of height 8, like the above, the first line has but 2 hash and 7 dots. The bottom line, meanwhile, has 9 hashes and 0 dots. Via what formula (or arithmetic, really) could you print that many dots?

{% endspoiler %}

### How to Test Your Code

Does your code work as prescribed when you input

* `-1` (or other negative numbers)?
* `0`?
* `1` through `23`?
* `24` or other positive numbers?
* letters or words?
* no input at all, when you only hit Enter?

{% next %}

## Removing the Dots

All that remains now is a finishing flourish! Modify `mario.c` in such a way that it prints spaces instead of those dots!

{% spoiler "Hint" %}

A space is just a press of your space bar, just as a period is just a press of its key! Just remember that `printf` requires that you surround both with double quotes!

{% endspoiler %}

{% next "Compile" %}

#### Compile your program
When you are done coding the above,  `compile` your program with the `make` command.

```
  $ make mario
```

##### DEBUG

You know by now that you will almost certainly experience errors when compiling. 
Do your best to work through the errors. Read the line numbers reported in the errors and go to the code and see what is coded on that line. It's always best to start with the **first** error that is reported. Sometimes fixing the first error fixes ALL of them. 
Remember to use `help50` as below if the error messages aren't clear. 

```csh
$ help50 make mario
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**mario**

To run the executable `mario` file you will type the following at the terminal prompt
````
$ ./mario
````

{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/mario/less
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
submit50 cs50/2018/ap/mario/less
```

