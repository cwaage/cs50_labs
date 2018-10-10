# cs50_labs

## Hello Again 
### Adding Interactive Features To Your Program 

Follow the 'TODO' prompts int the code's comments to accomplish the tasks listed below.

  - Add the cs50 library in as an include
  - Get User Input with the get_string() function
  - Print output using printf() with the %s string placeholder


{% spoiler "Help for get_string() Try first without clicking" %}
Be sure to declare your variable as type string and assign it the value from the get_string input as below

string variable_name = get_string("Bla bla bla);

{% endspoiler %}

#### Compile your program (Change your source code to machine code)
When you are done with the changes listed above
At the $ prompt type:

  make hello_again
  
{% next "Running Your Program" %}

#### Run Your Program
When you code has compiled without errors there will be a new 'executable' file created
To run that file you will type the following in the terminal prompt
  
$ ./hello_again

- Your program should generate the following output and then wait for your input 

Please enter your name: 

- Type your name and hit return 

Please enter your name: Chris Waage

- You should see the following output on your terminal 

Hello Chris Waage

{% check "Does your code compile?" %}
{{ if compiles.passed }}
Yes! Nicely done.
{% else %}
Looks like you have some errors to fix
{% endcheck %}

{% submit "Ready to submit?" %}
