# cs50_labs
## Practice Lab 1: Conditionals, Boolean Operators, Loops

### Conditionals 


{% next Boolean Operators %}
### Boolean Operators

```c
  &&  // and
  ||  // or
  !   // not
```
{% next Loops %}
### Loops

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

{% next Accumulating Variable Values with Loops %}
### Accumulating Variable Values with Loops

You can setup loops to continually update variables each time a loop executes.

#### Scope 

NOTE: There is a concept called **Scope**. Meaning if you declare your variable inside the loop,
it only exists within the loop's code. So declare it before the loop if it needs to be used
elsewhere in your code. 

```c

  // Variable declared before the loop
  int x = 10; 
  // For Loop
  for (int i = 0; i < 10; i++)
  {
    // Add 2 to x each time the loop executes
    x += 2;
  }
```
In the example above,  the value of `x` increases by two each time through the loop.

In your code, create a for loop that repeats 5 times and multiply the z variable by 4 each time through the loop. 
What will be the final value of z?


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


