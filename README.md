# cs50_labs
## Pennies

### Program Overview

If ever given the choice between $10,000,000 or a month’s worth of pennies, whereby you receive a penny the first day, two pennies the second, four pennies the third, and so forth … take the pennies. 

Why? Exponentiation. Those pennies add up. Consider how many pennies you’d receive on the 31st day alone, not to mention on the days leading up to it:

```
1 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2
  × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2
  × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2

  = 1073741824
 ```

Put more succinctly, that’s 1 × 2<sup>30</sup>. Convert those pennies to dollars (by dividing by 100) and you get, what, over $10,000,000 on just that day. 

What if you were given more than one penny on that first day? Or the month were February, in which case you’d get shortchanged a few million? (Best to take the pennies in January, March, May, July, August, October, or December.) Let’s find out.

Implement, in a file called `pennies.c`, a program that first asks the user how many days there are in the month and then asks the user how many pennies he or she will receive on the first day of that month. The program should then calculate the amount that the user will have received in total by the end of the month (**not just on the last day**) if that amount is doubled on every day but the first, expressed not as pennies but as dollars and cents. 

Note: If the user does not type in 28, 29, 30, or 31 for the number of days in the month, the program should prompt the user to retry. Note: If the user does not input a positive integer for the first day’s number of pennies, the program should prompt the user to retry.

For instance, your program might behave as follows, whereby underlined text represents some user’s input.

#### Command Line Input/Output 

```csh
~/workspace/unit1/pennies/ $ ./pennies
Days in month: 32
Days in month: 31
Pennies on first day: 1
$21474836.47
```
Notice how this output suggests that the program should indeed re-prompt the user if he or she fails to cooperate with these rules (as by inputting too many days).

{% next TODO 0 %}

Add the math.h header file to your source code. Why do we need it? 

{% next TODO 1 %}

TODO 1

Declare two variables specified in the commnets. Do not assignment them any values. Those will be assigned by the user as specified in the following TODO blocks. 

{% next TODO 2 %}

TODO 2 : Create a loop block that
  - A. Executes at least once
  - B. Assigns variable for number of days from user input 
  - C. Repeats Block (Loops) when the input value is less than 28 or more than 31
  
Which loop block is garanteed do execute at least once? A for loop, while loop, or do while loop?

{% spoiler Loop Syntax Reminder %}

```c
  // For Loop
  for (int i = 0; i < 10; i++)
  {
    // Code to execture in the loop 
  }
```

```c
  // While loop 
  while (x <= 20) // Enters loop and repeats when true 
  {
    // Code to execture in the loop 
  }
```

```c
  // Do While loop 
  do 
  {
    // Code to execture in the loop 
  }(x <= 20); // Repeats when true 
```

{% endspoiler %}

{% next TODO 3 %}

TODO 3 : Create a loop block that
  A. Executes at least once
  B. Assigns your variable for starting number of pennies from user input 
  C. Repeats Block (Loops) when the input value is less than 1

{% next TODO 4 %}

TODO 4 : Calculate total value after the number of days
 A. Assign that value to a long long variable 
 B. Note: Use the pow() function from the math.h library in your equation
 [pow() in math.h documentation](https://reference.cs50.net/math/pow)

{% spoiler Hint %}
{% endspoiler %}

{% next TODO 5 %}

TODO 5 : Convert from number of pennies to currency format in dollars

{% spoiler Hint %}
{% endspoiler %}

{% next TODO 6 %}

TODO 6 : Print with two decimal places for correct currency format (i.e. '$4.27)
Hopefully you are getting comfortable priting formatted doubles and floats to a specified decimal limit. 


