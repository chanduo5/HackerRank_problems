# Problem Statement: #

Determine if a Given Year is a Leap Year

An extra day is added to the calendar almost every four years as February 29, and the day is called a leap day. It corrects the calendar for the fact that our planet takes approximately 365.25 days to orbit the sun. A leap year contains a leap day.

In the Gregorian calendar, three conditions are used to identify leap years:
- The year can be evenly divided by 4, is a leap year, unless:
- The year can be evenly divided by 100, it is NOT a leap year, unless:
- The year is also evenly divisible by 400. Then it is a leap year.

This means that in the Gregorian calendar, the years 2000 and 2400 are leap years, while 1800, 1900, 2100, 2200, 2300, and 2500 are NOT leap years.

Task:

Given a year, determine whether it is a leap year. If it is a leap year, return the Boolean True, otherwise return False.

Note that the code stub provided reads from STDIN and passes arguments to the is_leap function. It is only necessary to complete the is_leap function.

### Input Format: ###

Read year, the year to test.

### Constraints: ###

1900 ≤ year ≤ 100000

### Output Format: ###

The function must return a Boolean value (True/False). Output is handled by the provided code stub.

## Solution: ##

Here is the solution using your code:
python

    def is_leap(year):
              # Initially set leap to False
    leap = False
    
               # Check if the year is divisible by 4
    if year % 4 == 0:
                # If divisible by 4, check if it's also divisible by 100
        if year % 100 == 0:
                # If divisible by 100, check if it's also divisible by 400
            if year % 400 == 0:
                # If divisible by 400, it's a leap year
                leap = True
        else:
             # If divisible by 4 but not by 100, it's a leap year
            leap = True
    
               # Return the result (True if leap year, False otherwise)
    return leap

               # Read input from user
     year = int(input())
               # Call the is_leap function and print the result
     print(is_leap(year))

## Explanation: ##

- Function Definition:

      def is_leap(year):
Defines a function is_leap that takes a single parameter year.

- Initialization:

      leap = False
Initializes a boolean variable leap to False. This will be used to store whether the given year is a leap year or not.

- Divisibility by 4 Check:

      if year % 4 == 0:
The first check is to see if the year is divisible by 4. If the remainder when the year is divided by 4 is 0 (year % 4 == 0), then we proceed to further checks.

- Divisibility by 100 Check:

      if year % 100 == 0:
If the year is divisible by 4, the next check is to see if it is also divisible by 100. If it is, we move to the next nested check.

- Divisibility by 400 Check:

      if year % 400 == 0:
        leap = True
If the year is divisible by both 4 and 100, we then check if it is also divisible by 400. If it is, we set leap to True because it satisfies all conditions to be a leap year.

- Else for Divisibility by 100:

      else:
        leap = True
If the year is divisible by 4 but not by 100, it is still a leap year. Therefore, we set leap to True in this case.

- Return the Result:

      return leap
Finally, the function returns the value of leap, which will be True if the year is a leap year and False otherwise.

- Input and Function Call:

      year = int(input())
      print(is_leap(year))
Reads an integer input from the user, calls the is_leap function with this input, and prints the result.
