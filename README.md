# cs50_labs
## ISDN 

### Program Overview

#### ISBN: What are they?

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

For instance, your program might behave as follows. The red text represents user input.

#### Command Line Input/Output 

Consider the below representative of how your own program should behave when passed a valid ISBN-10 (sans hyphens); underlined is some user’s input.

~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: red">0789751984</span><br />
YES<br />

Of course, get_long(“ISBN: “) itself will reject an ISBN-10’s hyphens (and more) anyway:

~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: red">0-789-75198-4</span><br />
ISBN: <span style="color: red">foo</span><br />
ISBN: <span style="color: red">0789751984</span><br />
YES<br />

But it’s up to you to catch inputs that are not ISBN-10s (e.g., Jenny’s[4] phone number), even if ten digits.

~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: red">5558675309</span><br />
NO<br />

Notice how this output suggests that the program should indeed re-prompt the user if he or she fails to cooperate with these rules (by inputting too many days).

{% next Pseudo Code %}

In the Text File pseudocode.txt write out the steps to complete this assignment.
When You have completed the process compare your pseudo code to the code hidden
by the "Spoiler" button below.

{% spoiler Spoiler: Pseudo Code Example %}
```txt
step 1  let num_pennies = user input
step 2  while num_pennies < 1
step 3          repeat step 1
step 4  let num_days = user input
step 5  while num_days < 29 or num_days > 31
step 6          repeat step 4
step 7  for each day
step 8          set num_pennies = num_pennies * 2
step 9  convert number of pennies to dollars
step 10 display acculuated num_pennies in $ format
```
Note any differences between your pseudo code and the code above. Think about those differences and how they might change the way you create your program. 

{% endspoiler %}

{% next TODO 0 %}

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
**Print with two decimal places for correct currency format (i.e. $4.27)**
Hopefully you are getting comfortable priting formatted doubles and floats to a specified decimal limit. 

{% next "Compile" %}

#### Compile your program
When you are done coding the above,  `compile` your program with the `make` command.

```
  $ make pennies
```

##### DEBUG

At this point you may see errors reported in the terminal. Don't worry, even expert programmers have to deal with compile errors on most of their programs. 
Do your best to work through any them. It's always best to start with the first error that is report. Sometimes fixing the first error fixes ALL of them. 

If the C compiler error messages are confusing to you, try using `help50`. This command is programmed by those smart Harvard folks
to generate more human readable debug and error messages. It can be helpful in pinpointing a problem. Use the command as shown below.

```csh
$ help50 make pennies
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**pennies**

You can run the list command at the terminal $ prompt to see all the files in the directory

```
ls
```

To run the executable `pennies` file you will type the following at the terminal prompt
````
$ ./pennies
````

Example Program Output below (Green text is user input).

~/workspace/unit1/pennies/ $ ./pennies<br />
Days in month: <span style="color: green"> 5 </span><br />
Days in month: <span style="color: green"> 30 </span><br />
Pennies on first day: <span style="color: green"> 0 </span><br />
Pennies on first day: <span style="color: green"> 2 </span><br />
$21474836.46<br />
<br />
Notice above how the output "Days in month:" and "Pennies on first day:" repeat to prompt the user to enter data within acceptable ranges


{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/pennies
```

#### Style

Check if you are stylistically correct by usng the 'style50' check below. This does *not* check for
syntax or other errors. It only checks if your code is inline with expected style requirements (spacing, indentations, etc...).

For Recommended Style Notes visit the following link [CS50 Style Guide](https://cs50.readthedocs.io/style/c/)

```
style50 pennies.c
```

#### Submit

After you have checked your style and syntax above you are ready to submit your code.
You can submit your project directly from the command line as shown below.

```
submit50 cs50/2018/ap/pennies
```

You will be prompted for your github credentials (user name/password) and at the end of the process may see a message like the following:

```csh
Files that will be submitted:
./pennies.c
Files that won't be submitted:
./.bash_history
./pennies
Keeping in mind the course's policy on academic honesty, are you sure you want to submit these files (yes/no)?
```

Type **yes** and you are done! 


