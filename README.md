# cs50_labs
## ISDN 

### Program Overview

#### ISBN: What are they?

As you may know, most any book that you borrow or buy has an International Standard Book Number, otherwise known as an ISBN or ISBN-10, "a 10-digit number that uniquely identifies books and book-like products published internationally." Books published since 2007 might also have an ISBN-13, a 13-digit number with a similar purpose, but never mind those.

Turns out you can mathmatically check if the ISBN-10 is a legitimate book identifier or if it's just a random phone number like the high school's, 3603762287.

#### Validating an ISBN

For the long version of how the validation of an ISDN is derived see the Harvard version of this problem [ISBN](https://docs.cs50.net/2018/ap/problems/isbn/isbn.html#readin-bookz).

The Short Version (which isn't actually short) goes like this: 

To validate an ISBN-10, multiply its first digit by 1, its second digit by 2, its third digit by 3, its fourth digit by 4, its fifth digit by 5, its sixth digit by 6, its seventh digit by 7, its eighth digit by 8, its ninth digit by 9, and it's tenth digit by 10. Take the sum of those products and then divide it by 11. If the remainder is equal to zero then it is a valid IBSN. 

More visually, an ISBN number like 0-789-75198-4 which is the ISBN for the book called *Absolute Beginner’s Guide to C* could be confirmed to be valid by using the steps shown below:

<hr />

**1**·0 + **2**·7 + **3**·8 + **4**·9 + **5**·7 + **6**·5 + **7**·1 + **8**·9 + **9**·8 + **10**·4 = 330

<hr />

Since 330 % 11 == 0, the number is indeed a legitimate ISBN-10. 

Mathmatically speaking, computing the validation check is not hard, but it does get a bit tedious by hand. 
If only there was some device we could program to automate the process for us. Hmm ... 


#### Command Line Input/Output 

Consider the below representative of how your own program should behave when passed a valid ISBN-10 (sans hyphens); underlined is some user’s input.
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">0789751984</span><br />
YES<br />
<hr />
Of course, get_long(“ISBN: “) itself will reject an ISBN-10’s hyphens (and more) anyway:
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">0-789-75198-4</span><br />
ISBN: <span style="color: brown">foo</span><br />
ISBN: <span style="color: brown ">0789751984</span><br />
YES<br />
<hr />
But it’s up to you to catch inputs that are not ISBN-10s, even if ten digits.
<hr />
~/workspace/unit1/isbn/ $ ./isbn<br />
ISBN: <span style="color: brown">5558675309</span><br />
NO<br />
<hr />


{% next TODO 0 %}

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

