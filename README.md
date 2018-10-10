# cs50_labs

## Hello Again 
### Adding Interactive Features To Your Program 

Follow the 'TODO' prompts int the code's comments to accomplish the tasks listed below.

  - Add the cs50 library in as an include
  - Get User Input with the get_string() function
  - Print output using printf() with the %s string placeholder


{% spoiler "Try first without peaking: Click for help with get_string()" %}
Be sure to declare your variable as type string and assign it the value from the get_string input as below

```
string name = get_string("Please enter your name: ");
```

{% endspoiler %}

{% spoiler "Try first without peaking: Click for help with printf() with %s placeholder" %}
Use

```
printf("Hello %s\n", name);
```

{% endspoiler %}

#### Compile your program (Change your source code to machine code)
When you are done with the changes listed above compile your program with the make command

{% spoiler "Try it yourself before clicking" %}
At the $ prompt type as shown below:

```
  $ make hello_again
```

{% endspoiler %}
  
{% next "Running Your Program" %}

#### Run Your Program
When you code has compiled without errors there will be a new 'executable' file called

**hello_again**

To run that file you will type the following in the terminal prompt
````
$ ./hello_again
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
{% submit "Ready to submit?" %}
