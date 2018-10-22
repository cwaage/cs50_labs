# cs50_labs
## Cash

{% video https://www.youtube.com/watch?v=sxXQ-jgUIg8 %}

{% next %}

## Greedy Algorithms

<!-- http://mypieceofthe31415927.blogspot.com/2014/04/whats-wrong-with-these-us-coins.html -->
![US coins](coins.jpg)

When making change, odds are you want to minimize the number of coins you're dispensing for each customer, lest you run out (or annoy the customer!).  Fortunately, computer science has given cashiers everywhere ways to minimize numbers of coins due: greedy algorithms.

According to the National Institute of Standards and Technology (NIST), a greedy algorithm is one "that always takes the best immediate, or local, solution while finding an answer. Greedy algorithms find the overall, or globally, optimal solution for some optimization problems, but may find less-than-optimal solutions for some instances of other problems."

What's all that mean? Well, suppose that a cashier owes a customer some change and in that cashier's drawer are quarters (25¢), dimes (10¢), nickels (5¢), and pennies (1¢). The problem to be solved is to decide which coins and how many of each to hand to the customer. Think of a "greedy" cashier as one who wants to take the biggest bite out of this problem as possible with each coin they take out of the drawer. For instance, if some customer is owed 41¢, the biggest first (i.e., best immediate, or local) bite that can be taken is 25¢. (That bite is "best" inasmuch as it gets us closer to 0¢ faster than any other coin would.) Note that a bite of this size would whittle what was a 41¢ problem down to a 16¢ problem, since 41 - 25 = 16. That is, the remainder is a similar but smaller problem. Needless to say, another 25¢ bite would be too big (assuming the cashier prefers not to lose money), and so our greedy cashier would move on to a bite of size 10¢, leaving him or her with a 6¢ problem. At that point, greed calls for one 5¢ bite followed by one 1¢ bite, at which point the problem is solved. The customer receives one quarter, one dime, one nickel, and one penny: four coins in total.

It turns out that this greedy approach (i.e., algorithm) is not only locally optimal but also globally so for America's currency (and also the European Union's). That is, so long as a cashier has enough of each coin, this largest-to-smallest approach will yield the fewest coins possible. How few? Well, you tell us!

{% next %}

{% spoiler Where To Code Cash %}

### Code Cash in the IDE 

In the IDE environment you will create your code and run it in the directory with the following path:
   `~workspace/unit1/cash`

To setup the directoy do the following:

  * Open another browser window (shortcut command + n)
  * Navigate to [https://cs50.io](https://cs50.io) and login
  * cd to `unit1`
  * `mkdir cash` and then cd into `cash`
  * create a new file called `cash.c` located in the `cash` directory
  * open `cash.c` in your IDE code editor window
  * With the Step by Step instructions open next your new window create your code
  * Remember in the IDE you need to save (shortcut: command + s ) your work before you compile it
  * Code well! 

{% endspoiler %}

## Implementation Details

Implement, in `cash.c` in the IDE, a program that first asks the user how much change is owed and then prints the minimum number of coins with which that change can be made.

* Use `get_float` to get the user's input and `printf` to output your answer. Assume that the only coins available are 
   * quarters (25¢)
   * dimes (10¢)
   * nickels (5¢)
   * pennies (1¢)
   
    * We ask that you use `get_float` so that you can handle dollars and cents, albeit sans dollar sign. In other words, if some customer is owed $9.75 (as in the case where a newspaper costs 25¢ but the customer pays with a $10 bill), assume that your program's input will be `9.75` and not `$9.75` or `975`. However, if some customer is owed $9 exactly, assume that your program's input will be `9.00` or just `9` but, again, not `$9` or `900`. Of course, by nature of floating-point values, your program will likely work with inputs like `9.0` and `9.000` as well; you need not worry about checking whether the user's input is "formatted" like money should be.
* You need not try to check whether a user's input is too large to fit in a `float`. Using `get_float` alone will ensure that the user's input is indeed a floating-point (or integral) value but not that it is non-negative.
* If the user fails to provide a non-negative value, your program should re-prompt the user for a valid amount again and again until the user complies.
* So that we can automate some tests of your code, be sure that your program's last line of output is only the minimum number of coins possible: an integer followed by `\n`.
* Beware the inherent imprecision of floating-point values. Go to the sandbox and run [`floats.c`](https://sandbox.cs50.io/575cd269-8b4e-4a01-bc9f-3de38614b43e)  if `x` is `2`, and `y` is `10`, `x / y` is not precisely two tenths! And so, before making change, you'll probably want to convert the user's inputted dollars to cents (i.e., from a `float` to an `int`) to avoid tiny errors that might otherwise add up! 
* Take care to round your cents to the nearest penny, as with `round`, which is declared in `math.h`. For instance, if `dollars` is a `float` with the user's input (e.g., `0.20`), then code like

  ```
  int coins = round(dollars * 100);
  ```

  will safely convert `0.20` (or even `0.200000002980232238769531250`) to `20`.

Your program should behave per the examples below.

```
$ ./cash
Change owed: 0.41
4
```

```
$ ./cash
Change owed: -0.41
Change owed: foo
Change owed: 0.41
4
```

{% spoiler "Hints" %}

{% video https://www.youtube.com/watch?v=2QZSsaSfB3A %}

{% endspoiler %}

### Staff's Solution

To try out the staff’s implementation of this problem, execute by copying and pasting the entire path below (including the tilde ~ into the terminal command line
```
~cs50/unit1/cash
```

### How to Test Your Code

Does your code work as prescribed when you input

* `-1.00` (or other negative numbers)?
* `0.00`?
* `0.01` (or other positive numbers)?
* letters or words?
* no input at all, when you only hit Enter?

{% next %}


#### Compile your program
When you are done coding the above,  `compile` your program with the `make` command.

```
  $ make cash
```

##### DEBUG

You know by now that you will almost certainly experience errors when compiling. 
Do your best to work through the errors. Read the line numbers reported in the errors and go to the code and see what is coded on that line. 

It's always best to start with the **first** error that is reported. Sometimes fixing the first error fixes ALL of them. 
For example if you forgot to declare `int x` but you use `x` in your code you might get a ton of errors that are basically asking `What is "x"!!!! You never declared it!!!`

Remember to use `help50` as below ONLY if the error messages aren't clear. 

```csh
$ help50 make cash
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**cash**

To run the executable `cash` file you will type the following at the terminal prompt
````
$ ./cash
````

{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/cash
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
submit50 cs50/2018/ap/cash
```

