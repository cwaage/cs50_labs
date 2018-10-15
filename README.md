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

  - **Note:** If the user does not type in 28, 29, 30, or 31 for the number of days in the month, the program should prompt the user to retry. 
  - **Note:** If the user does not input a positive integer for the first day’s number of pennies, the program should prompt the user to retry.

For instance, your program might behave as follows. The green text represents user input.

#### Command Line Input/Output 


~/workspace/unit1/pennies/ $ ./pennies<br />
Days in month: <span style="color: green"> 32 </span><br />
Days in month: <span style="color: green"> 31 </span><br />
Pennies on first day: <span style="color: green"> 1 </span><br />
$21474836.47<br />

Notice how this output suggests that the program should indeed re-prompt the user if he or she fails to cooperate with these rules (by inputting too many days).

#### TODO 0 :

  - Declare two variables specified in the comments. 
  - Do **not** assign them any values. 
  - Those will be assigned by the user as specified in the following TODO blocks. 

{% next TODO 1 %}

#### TODO 1 :
**Create a loop that:**
  - A. Executes at least once
  - B. Assigns variable that captures number of days in month from the user input 
  - C. Repeats Block (Loops) when the input value is less than 28 or more than 31
  
Which loop block is garanteed do execute at least once?

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

{% next TODO 2 %}

#### TODO 2 :
**Create a loop that:**
  - A. Executes at least once
  - B. Assign your variable for the initial number of pennies from the user input 
  - C. Repeats Block (Loops) when the input value is less than 1

{% next TODO 3 %}

#### TODO 3 : 
**Calculate total value after the number of days**
 
  - A. Create a `long long` variable as this could be a very very large number, depending on the initial value.
  - B. While you can caluclate the value with a formula, try using a for loop to calculate the value

{% spoiler Hint %}

```C
  // Create a for loop to repeat a total numer of times that is the same as the number of days in the month 
  for (/* Your Code Here */)
  {
    // Each time through the loop double the number of pennies
    // Reassign it to your long long variable 
  }
```
{% endspoiler %}

{% next TODO 4 %}

#### TODO 4 :
**Convert from number of pennies to currency format in dollars**

  - Your value calculated above is the total number of pennies. Do some math to convert number of pennies to dollars and cents?
  - You will be changing an long value to a decimal. You will need to create a new variable to capture the converted value. 
 
{% next TODO 5 %}

#### TODO 5 :
**Print with two decimal places for correct currency format (i.e. '$4.27)**
Hopefully you are getting comfortable priting formatted doubles and floats to a specified decimal limit. 


