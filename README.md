# cs50_labs
  
## Fahrenheit
### Using Input and C Operators

This lab will take you through the process of creating a program that
converts degrees in Celsius to Fahrenheit.

{% spoiler "Command Line" %}

The following is the input and output that will be generated when you successfully
run your completed program called `fahrenheit` in the terminal.

```
$ ./fahrenheit
C: 0
F: 32.0
```

**Note:** the **0** above is input by the user.

{% endspoiler %}

### Variable And Data Types

Variables store values so we can save data and reuse it later.
The C Programming language requires you to specify the type of a variable when you declare it.

For example, you declare and assign an int variable called `x` you as shown below:

```c
int x = 50;
```
For this program the variables that hold the values for the Celsius and Fahrenheit temps need to be expressed more percisely than integers, so you need to set their type as one that can store a decimal value.

{% spoiler List of Variable Types %}

```c
int // whole numbers
long long // whole numbers
float // decimals
double // decimals
char // single characters
bool // true / false ( defined in cs50.h )
string // string of characters ( defined in cs50.h )
```

{% endspoiler %}

{% next %}

### Getting Input from User

In `hello_again.c` you used the `cs50.h` function `get_string()` to get the user's name.

```c
    string name = get_string("Enter your name: ");
```

There are functions to get user input of nearly all types: `get_int`, `get_float`, `get_double`, `get_long`, `get_char`.
Pick the appropriate function to assign the variable of the Celsius value input from user.

### Formatting output with embedded placeholders.

{% spoiler "Placeholders by variable type" %}

```c
    %s // for string
    %i // for int
    %f // for float
    %lld // for long long
```
{% endspoiler %}

