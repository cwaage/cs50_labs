# cs50_labs
## Credit 

{% spoiler Where To Code Credit  %}

### Code Credit in the IDE 

In the IDE environment you will create your code and run it in the directory with the following path:
   `~workspace/unit1/credit`

To setup the directoy do the following:

  * Open another browser window (shortcut command + n)
  * Navigate to [https://cs50.io](https://cs50.io) and login
  * cd to `unit1`
  * `mkdir credit` and then cd into `credit`
  * create a new file called `credit.c` located in the `credit` directory
  * open `credit.c` in your IDE code editor window
  * With the Step by Step instructions open next your new window create your code
  * Remember in the IDE you need to save (shortcut: command + s ) your work before you compile it
  * Code well! 

{% endspoiler %}

# Credit

A credit (or debit) card, of course, is a plastic card with which you can pay for goods and services. Printed on that card is a number that's also stored in a database somewhere, so that when your card is used to buy something, the creditor knows whom to bill. There are a lot of people with credit cards in this world, so those numbers are pretty long: American Express uses 15-digit numbers, MasterCard uses 16-digit numbers, and Visa uses 13- and 16-digit numbers.  And those are decimal numbers (0 through 9), not binary, which means, for instance, that American Express could print as many as 10^15 = 1,000,000,000,000,000 unique cards! (That's, um, a quadrillion.)

Actually, that's a bit of an exaggeration, because credit card numbers actually have some structure to them. 

   * All American Express numbers start with 34 or 37
   * Most MasterCard numbers start with 51, 52, 53, 54, or 55
   * All Visa numbers start with 4

## Checksum

But credit card numbers also have a "checksum" built into them, a mathematical relationship between at least one number and others. That checksum enables computers (or humans who like math) to detect typos (e.g., transpositions), if not fraudulent numbers, without having to query a database, which can be slow. Of course, a dishonest mathematician could certainly craft a fake number that nonetheless respects the mathematical constraint, so a database lookup is still necessary for more rigorous checks.

## Luhn's Algorithm 

So what's the secret formula?  Well, most cards use an algorithm invented by Hans Peter Luhn of IBM. According to Luhn's algorithm, you can determine if a credit card number is (syntactically) valid as follows:

1. Multiply every other digit by 2, starting with the number's second-to-last digit, and then add those products' **digits** together.
1. Add the sum to the sum of the digits that weren't multiplied by 2.
1. If the total's last digit is 0 (or, put more formally, if the total modulo 10 is congruent to 0), the number is valid!

That's kind of confusing, so let's work through an example with an actual Visa number: 4003600000000014.

1. For the sake of discussion, let's first underline every other digit, **starting with the number's second-to-last digit**:
   
   <u>4</u>0<u>0</u>3<u>6</u>0<u>0</u>0<u>0</u>0<u>0</u>0<u>0</u>0<u>1</u>4

   Okay, let's multiply each of the underlined digits by 2:

   1•2 + 0•2 + 0•2 + 0•2 + 0•2 + 6•2 + 0•2 + 4•2

   That gives us:

   2 + 0 + 0 + 0 + 0 + 12 + 0 + 8

   Now let's add those products' **digits** (i.e., not the products themselves) together:

   2 + 0 + 0 + 0 + 0 + 1 + 2 + 0 + 8 = 13 (Notice we didn't at 12 from above, but 1 + 2)

1. Now let's add that sum (13) to the sum of the digits that weren't multiplied by 2 (starting from the end):

   13 + 4 + 0 + 0 + 0 + 0 + 0 + 3 + 0 = 20

1. Yup, the last digit in that sum (20) is a 0, so that card is indeed legit!

So, validating credit card numbers isn't hard, but it does get a bit tedious by hand. Luckily, you know how to code so you can automate this process.

## Implementation Details 

In `credit.c` in your IDE, write a program that prompts the user for a credit card number and then reports (via `printf`) whether it is a valid American Express, MasterCard, or Visa card number, per the definitions of each's format herein. So that we can automate some tests of your code, we ask that your program's last line of output be:

   * `AMEX\n`
   * `MASTERCARD\n`
   * `VISA\n` 
or  ...
   * `INVALID\n`

...nothing more, nothing less. 

For simplicity, you may assume that the user's input will be entirely numeric (i.e., devoid of hyphens, as might be printed on an actual card). But do not assume that the user's input will fit in an `int`! Best to use `get_long_long` from CS50's library to get users' input. (Why?)

Consider the below representative of how your own program should behave when passed a valid credit card number (sans hyphens).

```
$ ./credit
Number: 4003600000000014
VISA
```

Now, `get_long_long` itself will reject hyphens (and more) anyway:

```
$ ./credit
Number: 4003-6000-0000-0014
Number: foo
Number: 4003600000000014
VISA
```

But it's up to you to catch inputs that are not credit card numbers (e.g., a phone number), even if numeric:

```
$ ./credit
Number: 6176292929
INVALID
```

Test out your program with a whole bunch of inputs, both valid and invalid. Here are a [few card numbers](https://developer.paypal.com/docs/classic/payflow/payflow-pro/payflow-pro-testing/#credit-card-numbers-for-testing) that PayPal recommends for testing.

** Note ** There are a few Mastercard numbers listed at the link above that start with 22 like the following: 2221000000000009
With the algorithm described above, those numbers should be found to be `INVALID` by your program as they do not start with 51, 52, 53, 54, or 55. 

If your program behaves incorrectly on some inputs (or doesn't compile at all), time to debug!

{% spoiler "Staff's Solution" %}

To try out the staff’s implementation of this problem, execute by copying and pasting the entire path below (including the tilde ~ into the terminal command line

```
~cs50/unit1/credit 
```

{% endspoiler %}

{% next %}

#### Compile your program
Use the `make` command to compile your code.
```
  $ make credit 
```

##### DEBUG

Remember to read the line numbers reported in the errors and go to the code and see what is coded on that line. 

It's always best to start with the **first** error that is reported. Sometimes fixing the first error fixes ALL of them. 
For example if you forgot to declare `int x` but you use `x` in your code you might get a ton of errors that are basically asking `What is "x"!!!! You never declared it!!!`

Remember to use `help50` as below IF the error messages aren't clear. 

```csh
$ help50 make credit
```

{% next "Running Your Program" %}

#### Run Your Program

To run the executable `credit` file you will type the following at the terminal prompt
````
$ ./credit
````

{% next "Check, Style and Submit" %}

#### Check50
```
check50 cs50/2018/ap/credit
```

#### Style50
```
style50 credit.c
```

#### Submit50
```
submit50 cs50/2018/ap/credit
```

