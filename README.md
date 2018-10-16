# cs50_labs
## Practice Lab 1: Conditionals, Boolean Operators, Loops

Complete each section below.
Compile and run after you complete each section to see the results.

Compile
```
make practice_lab_1
```

Run
```
./practice_lab_1
```
{% next Conditionals %}

### Conditionals 

Two `int` variables are declared and assigned for you. 

```c
    int num1 = 20;
    int num2 = 30;
```
First Remove the two lines of code that comment out the section. 

Then below the variable declaration complete the `if ... else if ... else` conditional block that tests 
  - if num1 is greater than num2
  - else if num 2 is greater than num1
  - else // All other cases 
  
Compile and Run to see your output

When your code executes correctly, try changing values of num1 and num2 to generate a different result. 

Click the button below to see example code.

{% spoiler Conditional Example Code %}

```c
int num1 = 0;
int num2 = 5;
int num3 = 10;

if (num1 > num2) // Execute if num1 > num2 is TRUE 
{
  printtf("num1 is greater than num2\n");
}
else if (num1 > num3) // Executes when num1 > num3 is TRUE  
{
  printtf("num1 is greater than num3\n");
}
else // Executes only when all if and else if blocks above are FALSE
{
  printtf("num1 is not greater than num2 or num3\n");
}

```
{% endspoiler %}

{% next Boolean Operators %}

### Boolean Operators

In this sectin you will add boolean expressions that incorporate boolean operators 

```c
  &&  // and
  ||  // or
  !   // not
```

You can use boolean operators to test for multiple conditions in a single boolean expression.

**AND**

Both conditions must be true for the boolean expression to be evaluated as true

Example:
```c
if (x > y && x > z) // Evaluates to TRUE if x is BOTH either greater than y AND greater than z
```

**OR**

Only one conditions must be true for the boolean expression to be evaluated as true

Example: 
```c
if (x > 20 || x < 0) // Evaluates to TRUE if x is either greater than 20 or less than 0
```

**Not**

Negates the value or operator

Example:
```c
if (x != 20) // Evalues to true when x is not equal to 20
```

To complete this section: 

First Remove the two lines of code that comment out the section. 

Then complete the code using boolean operators to test for the maximum value of the three variables x, y, z
  - In the 'if' block code a boolean expression that will check if x is greater than both y and z.
  - In the `else if` block code a boolean expression that will check if y is greater than both x and z
  - In the `else` block code the print statment declaring the max (which variable must be max if above blocks are FALSE)

{% next Loops %}
### Loops

In this section you will create three different type of loops:

  - do while
  - while
  - for

First Remove the two lines of code that comment out the section. 

Then code the loops below as specified.

#### do while
For this loop, have your loop code execute only once, by coding the **boolean expression** set in the while(**boolean expression**)
to evaluate to FALSE.

#### while
Create a while loop that repeats a message 4 times.
Note: Remember to increment/decrement your control variable each time through the loop be sure it terminates (i.e. doesn't cause an infinite loop).

#### for
Create a for loop that loops 8 times and prints a message each time through the loop 

You can refer to syntax for each loop type by clicking the button below  

{% spoiler Loop Syntax Reminder %}

```c
    /* ---------------------------------------- */
    // do while loop
    // Always enter loop block at least once
    // Repeats while the boolean expression is TRUE
    /* ---------------------------------------- */
    int x = 9;
    do
    {
        printf("do while loop: x equals %i\n", x);
        x++; // x increments by one
    } while(x < 10);
    /* ---------------------------------------- */

    /* ---------------------------------------- */
    // while loop
    // Only Enter and Repeat when boolean expression is TRUE
    /* ---------------------------------------- */
    int y = 25; // Control Variable 
    while (y > 20)
    {
        printf ("while loop: y = %i\n", y);
        y -= 1; // Decrement y by one each time through the loop
    }
    /* ---------------------------------------- */


    /* ---------------------------------------- */
    // for loop
    /* ---------------------------------------- */
    // Repeat Loop 7 times
    for (int i = 0; i < 7; i++)
    {
        printf("for Loop Count = %i\n", i + 1);
    }
```

{% endspoiler %}

{% next Accumulating Variable Values with Loops %}
### Accumulating Variable Values with Loops

In this section will create a loop that continually updates a variable each time the loop is executed. 

Example: 

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

First Remove the two lines of code that comment out the section. 

Then in your code, create a for loop that repeats 3 times and multiply the z variable by 4 each time through the loop. 

{% spoiler Hint for Updating Value %}

Both of the following multiply z by 3 and then reassign z the result

```c
z *= 3;

```
```c
z = z * 3;
```

{% endspoiler %}

What will be the final value of z? Uncomment out the printf statement at the end of the section to check. 

#### Pennies

You should now be ready to complete `pennies.c`

Click on the link below to start coding
    -[pennies_lab](https://lab.cs50.io/cwaage/cs50_labs/unit1/pennies1/)


