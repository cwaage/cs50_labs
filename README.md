# AP CSP: cs50_labs

## Mini Lab
### Formatted Printing and Operators 

This mini lab is designed to give you hands on practice with printf() and math operators.

Use this Guide and the TODO notes in the code's comments to complete the tasks in each section. 

Compile and run after each section to check if your code is working correctly.

There is no `check50` for this assignment, but you can run `help50` when you compile your program:

```
$ help50 make unit1_practice_lab_0.c
```

{% next First TODO 0 %}

### Practice with Formatted printing and get functions.

Think of three types of information to ask a user.

    - One represented as a string
    - One by as an int
    - One by a float

In the first TODO section in your code create an int variable, a float variable, and a string variable.

Ask your user to input information that will be assigned to each of those variables using the get_int(), get_float(), and get_string() functions.


{% spoiler "get_int example" %}

```c
    int fingers = get_int("How many fingers do you have ");
```
{% endspoiler %}

#### Print Variable Values with Placeholders 

Print to output each of those in a single printf() statement. You will have to use multiple placeholders in a single printf() and include your variables after the quote as shown in the example below.

{% spoiler "printf() Example" %}

The placeholders `%s` , `%i`, and `%f` in the example below will be filled in with the variable values contained in the variables `name`, `age`, and `shoe_size`

```c
printf("Your name is %s and your are %i years old. You wear size %f shoes.\n", name, age, shoe_size);
```
{% endspoiler %}

{% next TODO 1 %}

### Math Operators

In the next TODO section you will practice coding some math operations in C
by creating int variables to capture each of the equations below.

    - 1 + 2 * 3 + 7 * 2 % 5
    - 2 + 3 * 4 - 6
    - 14 / 7 * 2 + 30 / 5 + 1
    - (12 + 3) / 4 * 2
    - (18 - 7) * (43 % 10)

{% spoiler "Example" %}
```c
int eq0 = 1 + 2 * 3 + 7 * 2 % 5;
int eq1 = 2 + 3 * 4 - 6;
```

{% endspoiler %}

{% next TODO 2 %}

After you have coded each of the equations and assigned them to variables, create a printf() statement that 

    - displays your **predicted** value for each equation 
    - and the actual value as calculated by C

    
{% spoiler "Example" %}
```c
printf("I predict eq0 will equal 2. C calcualtes eq0 to be %i\n", eq0);
```

{% endspoiler %}

If your predicted value is different, don't fret. Just try to understand why there's a mismatch. 
If your predicted value is the same ... you get a Gold Star. Brag to your friends. 

When you have completed the above, comtinue on with the Fahenheit assignment listed at the link below.

[Fahenheit](https://lab.cs50.io/cwaage/cs50_labs/operators/fahrenheit/)
