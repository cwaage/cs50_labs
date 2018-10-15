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

### Conditionals 

Declare and assign values to two `int` variables

```c
    int num1 = 20;
    int num2 = 30;
```

In the code on the right complete the `if ... else if ... else` conditional block
that tests 
  - if num1 is greater than num2
  - else if num 2 is greater than num1
  - else // All other cases 

Click the button below to see example code.

{% spoiler Conditional Example Code %}

```c
int num1 = 0;
int num2 = 5;
int num3 = 10;

// if block: Execute if num1 > num2 is TRUE 
if (num1 > num2)
{
  // Given the values above does this print?
  printtf("num1 is greater than num2\n");
}

// if ... else
if (num1 > num2) // Execute if num1 > num2 is TRUE 
{
  printtf("num1 is greater than num2\n");
}
else // Executes when num1 > num2 is FALSE  
{
  printtf("num1 is less than or equal to num2\n");
}

// if ... else ...  if ... else
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
Complete the code for this section to test for the maximum value of the three variables x, y, z
  - The if block's boolean expression will check if x is greater than both y and z.
  - The else if block's boolean expression will check if y is greater than both x and z
  - The else block will print the only remaining option (which variable must be max if above blocks are FALSE)

{% next Loops %}
### Loops

In this section create the three different type of loops we have discussed

  - do while
  - while
  - for

#### do while
For this loop, have you code execute only once, by coding the **boolean expression** set in the while(**boolean expression**)
evaluate to false.

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





