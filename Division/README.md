# Problem Description #

You need to write a Python program that reads two integers 𝑎 and 𝑏 from the standard input (the console). Once you have these two integers, you need to perform two types of division:

- Integer Division: This is the division where the fractional part (decimal) is discarded. In Python, this can be performed using the // operator.

- Float Division: This is the standard division where the fractional part is kept. In Python, this can be performed using the / operator.

Your program should output the results of these two divisions on two separate lines.

## Task ##

- Read two integers 𝑎 and 𝑏 from the input.

- Perform integer division 𝑎//𝑏 and print the result.

- Perform float division 𝑎/𝑏 and print the result.

No rounding or formatting is necessary.

## Example ##
Let's take a quick look at an example:

- If the input values are 𝑎=31 and 𝑏=5:

- Integer Division: 31//5 results in 6 (the decimal part is discarded).

- Float Division: 31/5 results in 6.2.

So, the output would be:

6
6.2



## Solution ##
Here’s how you can implement this in Python:

python

    if __name__ == '__main__':
      a = int(input())
      b = int(input())
    
    integer_division = a // b
    float_division = a / b
    
    print(integer_division)
    print(float_division)

## Detailed Steps ##

- Input Handling:

     Use input() to read the input values.

     Convert the inputs to integers using int().

- Perform the Calculations:

    Use // for integer division.

    Use / for float division.

- Print the Results:

    Print the result of the integer division.

    Print the result of the float division.
