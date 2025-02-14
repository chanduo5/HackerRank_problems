## Problem Description: ##

You are given a positive integer n. Depending on the value of n, you need to perform the following actions:

-If n is odd, print "Weird".
-If n is even and in the inclusive range of 2 to 5, print "Not Weird".
-If n is even and in the inclusive range of 6 to 20, print "Weird".
-If n is even and greater than 20, print "Not Weird".

# Input Format: #

A single line containing a positive integer n.

# Constraints: #

1 ≤ n ≤ 100

# Output Format: # 

Print "Weird" if the number is weird according to the given conditions. Otherwise, print "Not Weird".

# Steps to Solve the Problem: #

-Read the integer input n.

-Check if n is odd or even.

   Use the modulus operator % to determine if n is odd (n % 2 != 0).

-Based on the value of n, print the appropriate output.
 
  If n is odd, print "Weird".

  If n is even:

  If n is in the range 2 to 5, print "Not Weird".

  If n is in the range 6 to 20, print "Weird".

  If n is greater than 20, print "Not Weird".

# Code Implementation: #

python

    import math
    import os
    import random
    import re
    import sys

    if __name__ == '__main__':
    n = int(input().strip())

    if n % 2 != 0:  # Check if n is odd
        print("Weird")
    elif n % 2 == 0 and 2 <= n <= 5:  # Check if n is even and in range 2 to 5
        print("Not Weird")
    elif n % 2 == 0 and 6 <= n <= 20:  # Check if n is even and in range 6 to 20
        print("Weird")
    elif n % 2 == 0 and n > 20:  # Check if n is even and greater than 20
    print("Not Weird")


# Detailed Explanation: #

-The if __name__ == '__main__': line ensures that the code block runs only if the script is executed directly and not when imported as a module.

-n = int(input().strip()) reads the input, strips any leading/trailing whitespace, and converts it to an integer.

-The series of if-elif statements check the conditions one by one:

-If n is odd (n % 2 != 0), it prints "Weird".

  If n is even and in the range 2 to 5 (2 <= n <= 5), it prints "Not Weird".

  If n is even and in the range 6 to 20 (6 <= n <= 20), it prints "Weird".

  If n is even and greater than 20 (n > 20), it prints "Not Weird".
