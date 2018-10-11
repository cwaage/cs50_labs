# cs50_labs
  
## Fahrenheit
### Using Input and C Operators

This lab will take you through the process of creating a program that
converts degrees in Celsius to Fahrenheit.

To function succesfully it needs to do the following:

  - Declare a variable to store input from the user
  - Get input from the user
  - Do some math to convert Celsius to Fahrenheit
  - Output converted temperature in Fahenheit to one decimal place (i.e. 32.0) 

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

{% next %}

### Declaring your Celsius Variable
#### Variable And Data Types

Variables store values so we can save data and reuse it later.
The C Programming language requires you to specify the type of a variable when you declare it.

For example, you declare and assign an int variable called `x` you as shown below:

```c
int x = 50;
```
For this program the variables that hold the values for the Celsius and Fahrenheit temps need to be expressed more percisely than integers, so you need to set their type as one that can store a decimal value.

{% spoiler List of Variable Types %}

```c
int // whole numbers (4 bytes)
long long // whole numbers (8 bytes)
float // decimals (4 bytes)
double // decimals (8 bytes)
char // single characters (1 byte)
bool // true / false ( defined in cs50.h ) (1 bytes)
string // string of characters ( defined in cs50.h ) (4 or 8 bytes)
```

{% endspoiler %}

{% next %}

### Getting Input from User

In `hello_again.c` you used the `cs50.h` function `get_string()` to get the user's name.

```c
    string name = get_string("Enter your name: ");
```

There are functions to get user input of nearly all types: `get_int`, `get_float`, `get_double`, `get_long`, `get_char`.
Pick the appropriate function to assign your Celsius variable the value input from user.

{% next %}

### Do The Math
#### Using operators to convert

The formula for converting Fahrenheit to Celsius written out the long way looks something like ...

Celsius (°C) temp, multiplied by 9, divided by 5, and then add 32. The result is the equivalent temperature in degrees Fahrenheit (°F). For the more visually inclined, click the button below:

{% spoiler "Formula" %}

```c
  F = ((C * 9) / 5) + 32
```
{% endspoiler %}

Code the convertion, assigning the a variable the converted value 

{% next %}

### Formatting output with embedded placeholders.

{% spoiler "Placeholders by variable type" %}

```c
    %s // for string
    %i // for int
    %f // for float
    %lld // for long long
```
{% endspoiler %}

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string name = get_string("Enter your name: ");
    printf("hello, %s\n", name);
}
```

{% spoiler "Hint for get_string()" %}
Declare your variable as type `string` and assign it the value from the `get_string()` function as below.
Remember: the `get_string()` gets the data from the user, but you need a `string` variable to store that data.

```c
string name = get_string("Please enter your name: ");
```

{% endspoiler %}

{% spoiler "Hint for printf() with placeholder" %}
The `%s` is needed in the `printf()` as a placeholder for the user data stored in the `name` variable,
which is typed after the close of the quotes and comma as shown below:

```c
printf("Hello %s\n", name);
```

{% endspoiler %}

{% next "Compile" %}

#### Compile your program
When you are done with the changes listed above `compile` your program with the `make` command.
**NOTE**: There is no *save* in the lab programming environment. Your program saves automatically as it goes.

{% spoiler "Hint for compile" %}
At the terminal $ prompt type the command as shown below:

```
  $ make fahrenheit
```
{% endspoiler %}

##### DEBUG

At this point you may see errors appear in the output. This should be getting familiar, and you know not to panic. I hope.
Do your best to work through any errors. It's always best to start with the first error that is listed.

If the C compiler error messages are confusing to you, try using `help50` (yes yet another command). This command is programmed
to generate more human readable debug and error messages. It can be helpful in pinpointing a problem. Use the command as shown below.

```csh
$ help50 make fahrenheit
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**fahrenheit**

You can run the list command at the terminal $ prompt to see all the files in the directory

```
ls
```

To run the executable `fahrenheit` file you will type the following at the terminal prompt
````
$ ./fahrenheit
````
- Your program should generate the following output and then wait for your input

```
C:
```
- Type a temperature as below
```
C: 100
```
- You should see the following output on your terminal
```
F: 212.0
```
{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/fahrenheit
```

#### Style

Check if you are stylistically correct by usng the 'style50' check below. This does *not* check for
syntax or other errors. It only checks if your code is inline with expected style requirements (spacing, indentations, etc...).

For Recommended Style Notes visit the following link [CS50 Style Guide](https://cs50.readthedocs.io/style/c/)

```
style50 fahrenheit.c
```

#### Submit

After you have checked your style and syntax above you are ready to submit your code.
You can submit your project directly from the command line as shown below.

```
submit50 cs50/2018/ap/fahrenheit
```

You will be prompted for your github credentials (user name/password) and at the end of the process may see a message like the following:

```csh
Files that will be submitted:
./hello.c
Files that won't be submitted:
./.bash_history
./hello
Keeping in mind the course's policy on academic honesty, are you sure you want to submit these files (yes/no)?
```

Type 'yes' and you are done!
