# cs50_labs

## Hello Again 
### Adding User Data To Your Program 

*Hello Orcas AP CSPers. I have been experimenting with this new feature for the class. 
It's a step by step interactive lab which looks pretty slick. Try it out and let me
know what you think. - C Waage*

Follow the 'TODO' prompts in the code's comments to accomplish the tasks listed below.

  - Add the cs50 library in as an include
  - Create a string variable called `name`
  - Get User Input with the `get_string()` function
  - Print output using `printf()` with the `%s` string placeholder

See how far you can get on your own. But if you forget some keywords or syntax, or it's simply just not working ...
don't hit your head against a wall. Click on the hints listed below and help will be revealed. 

{% spoiler "Hint for cs50.h" %}

To include a header file use the #include and the file name as shown below 

```c
#include <cs50.h>
```
{% endspoiler %}

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

{% spoiler "Hint for compile" %}
At the $ prompt type the command as shown below:

```
  $ make hello
```




{% endspoiler %}

##### DEBUG

At this point you may see errors appear in the output. Don't Panic! This is all part of the coding process.
Do your best to work through any errors. It's always best to start with the first error that is listed.

If the C compiler error messages are confusing to you, try using `help50` (yes yet another command). This command is programmed
to generate more human readable debug and error messages. It can be helpful in pinpointing a problem. Use the command as shown below. 

```csh
$ help50 make hello
```
  
{% next "Running Your Program" %}

#### Run Your Program
When you code has compiled without errors there will be a new 'executable' file called

**hello**

To run that file you will type the following in the terminal prompt
````
$ ./hello
````
- Your program should generate the following output and then wait for your input 

````
Please enter your name: 
````
- Type your name and hit return 
````
Please enter your name: Chris Waage
````

- You should see the following output on your terminal 
````
Hello Chris Waage
````
{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/fall/hello
```

#### Style

Check if you are stylistically correct by usng the 'style50' check below. This does *not* check for
syntax or other errors. It only checks if your code is inline with expected style requirements (spacing, indentations, etc...).

For Recommended Style Notes visit the following link [CS50 Style Guide](https://cs50.readthedocs.io/style/c/)

```
style50 hello.c
```

#### Submit

After you have checked your style and syntax above you are ready to submit your code. 
You can submit your project directly from the command line as shown below. 

```
submit50 cs50/2018/fall/hello
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

Congrats, you just finished our first Coding lab. 
