# cs50_labs
## ISBN 

### Program Overview

Click on Button below to get detailed information on where to code isbn.c

{% spoiler Where To Code ISBN %}

# ISBN 

### Don't Code ISBN In The Sandbox Environment

It is time to transition to coding in the IDE located at [https://cs50.io](https//:cs50.io)

The Sandbox has been a nice initial coding environment, but it has been a little buggy, and
it does not allow you retain your files in an organized hierarchy.

For the ISBN problem do the following:

  * Use the step by step instructions located at the left
  * Open another browser window (shortcut command + n)
  * Navigate to [https://cs50.io](https://cs50.io) and login
  * cd to unit1 
  * mkdir isbn and then cd into isbn
  * create a new file called isbn.c located in the isbn directory
  * open isbn.c in your IDE code editor window
  * With the Step by Step instructions open next your new window create your code
  * Remember in the IDE you need to save (shortcut: command + s ) your work before you compile it
  * Happy Coding!

{% endspoiler %}

#### ISBN: What are they?

As you may know, most any book that you borrow or buy has an International Standard Book Number, otherwise known as an ISBN or ISBN-10, "a 10-digit number that uniquely identifies books and book-like products published internationally." Books published since 2007 might also have an ISBN-13, a 13-digit number with a similar purpose, but never mind those.

Turns out you can mathmatically check if the ISBN-10 is a legitimate book identifier or if it's just a random phone number like the high school's, 3603762287.

#### Validating an ISBN

For the long version of how the validation of an ISBN is derived see the Harvard version of this problem [ISBN](https://docs.cs50.net/2018/ap/problems/isbn/isbn.html#readin-bookz).

The Short Version (which isn't actually that short) goes like this: 

To validate an ISBN-10, multiply its first digit by 1, its second digit by 2, its third digit by 3, its fourth digit by 4, its fifth digit by 5, its sixth digit by 6, its seventh digit by 7, its eighth digit by 8, its ninth digit by 9, and it's tenth digit by 10. Take the sum of those products and then divide it by 11. If the remainder is equal to zero then it is a valid IBSN. 

More visually, an ISBN number like 0-789-75198-4 which is the ISBN for the book called *Absolute Beginner’s Guide to C* could be validated using the steps shown below:

<hr />

**1**·0 + **2**·7 + **3**·8 + **4**·9 + **5**·7 + **6**·5 + **7**·1 + **8**·9 + **9**·8 + **10**·4 = 330

<hr />

Since 330 % 11 == 0, the number is indeed a legitimate ISBN-10. 

Mathmatically speaking, validating the number is not hard, but it does get a bit tedious by hand. 
If only there was some device we could program to automate the process for us. I wonder what that might look like ...

{% next Program Overview %}

#### Program Overview

Create a file called isbn.c inside ~/workspace/unit1/isbn, in which you should write a program that prompts the user for an ISBN-10 and then reports (via printf) whether the number’s legit. So the automated checks work on your code, your program’s last line of output should be either `YES\n` or `NO\n`, nothing more, nothing less.

  * Get ISBN from the user
  * Isolate each digit in the number and multiply it by it's respective order in the ISBN
  * Accumulate the sum of each digit's products as visually shown in the section above
  * Check if the accumulated sum % 11 is equal to 0
  * Print "YES" if it is equal to 0
  * Otherise print "NO"

#### Getting the number from the user

Remember that a signed int has a max value of `2,147,483,647`. Being that ISBN's are 10 digit's in length, it is quite conceivable that you would have an overflow issue with some ISBN's. So, which `type` should you use for your ISBN variable? It should be a whole number that stores twice as many bytes as an 'int'. Double, float, char, long long, or string?? (See cryptic and subtle hint below).
```c
long long
```
There's even a function programmed for you to get a long long value from user input.
```c
get_long_long("Prompt message written to output");
```
#### Traversing The ISBN: Looping to isolate each digit 

How are you going to get the values for each individual digit? One way is to construct a loop and utilize a couple of tricks to help isolate each digit. 

#### Isolating the each digit in the number

To get the one's place of any number you can use the modulus operator like below

```md
n % 10
```
**For Example**
```md
354 % 10 = 4
```
Because thanks to modular math `354 / 10` yields `35` with a remainder of `4`

Great. That get's you *one* digit, but what about the rest.

*Turns out* ... your can truncate an `integer` or `long long` by removing the one's place by dividing that number by 10 as shown below.

```md
354 / 10 = 35.
```
Now you can isolate the next digit using the modulus trick described above.

```md
35 % 10 = 5
```
{% next Next: Constructing The Loop %}

#### The Loop

The key to successfully completing this program is to put some thought into how you construct a loop and update variables within the loop. 

##### Hints

* Your loop needs to repeat so every digit in the ISBN is examined
* Each time through the loop isolate the one's place using the tricks described above
* Create a variable that updates each time through the loop to multiply your isolated digit by the apporpriate value
* Store your accumlated sum in a variable

##### Compile and Test Incrementally

Don't wait until you have attempted to create your entire program to compile and test your code. After you complete each section, perform a compile to check if you have introduced and errors. Then run the program to see if you output is what you expect.

Compile
```
  $ make isbn
```
Run
````
$ ./isbn
````
  
#### Command Line Input/Output 

When your program is complete your output should look like the example shown below when passed a valid ISBN-10 (sans hyphens); brown text is some user’s input.
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">0789751984</span><br />
YES<br />
<hr />
Luckily, get_long(“ISBN: “) will reject an ISBN-10’s hyphens (and more) so you don't have to program a loop to check for non-valid input.
That function has been abstracted away by the helpful coder of the get_long_long function. 
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">0-789-75198-4</span><br />
ISBN: <span style="color: brown">foo</span><br />
ISBN: <span style="color: brown ">0789751984</span><br />
YES<br />
<hr />
But it’s up to you to catch inputs that are not ISBN-10s, even if it is ten digits.
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">5558675309</span><br />
NO<br />
<hr />

{% next "Compile" %}

#### Compile your program
When you are done coding the above,  `compile` your program with the `make` command.

```
  $ make isbn
```

##### DEBUG

At this point you may see errors reported in the terminal. Don't worry, even expert programmers have to deal with compile errors on most of their programs. 
Do your best to work through any them. It's always best to start with the first error that is report. Sometimes fixing the first error fixes ALL of them. 

If the C compiler error messages are confusing to you, try using `help50`. This command is programmed by those smart Harvard folks
to generate more human readable debug and error messages. It can be helpful in pinpointing a problem. Use the command as shown below.

```csh
$ help50 make isbn
```

{% next "Running Your Program" %}

#### Run Your Program
When your code has compiled without errors there will be a new 'executable' file called

**isbn**

To run the executable `isbn` file you will type the following at the terminal prompt
````
$ ./isbn
````

{% next "Check, Style and Submit" %}

#### Check
You can use the 'check50' command as shown below to check if your syntax and function are correct

```
check50 cs50/2018/ap/isbn
```

#### Style

Check if you are stylistically correct by usng the 'style50' check below. This does *not* check for
syntax or other errors. It only checks if your code is inline with expected style requirements (spacing, indentations, etc...).

For Recommended Style Notes visit the following link [CS50 Style Guide](https://cs50.readthedocs.io/style/c/)

```
style50 isbn.c
```

#### Submit

After you have checked your style and syntax above you are ready to submit your code.
You can submit your project directly from the command line as shown below.

```
submit50 cs50/2018/ap/isbn
```

