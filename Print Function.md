# Problem Statement #

The task is to print a sequence of integers from 1 to n (inclusive) as a single string without using any string methods. Here are the key points:

- Read an integer n from standard input.
- Output the integers from 1 to n consecutively without any spaces.

### Example ###
For example, if the input is 5, the output should be:

12345
## Constraints ##

The constraints are:

1 ≤ 𝑛 ≤ 150

## Code Explanation ##
Here's the completed code:
python

    if __name__ == '__main__':
      n = int(input())
      for i in range(1, n + 1):
       print(i, end='')


## Detailed Explanation ##

-  ### Reading Input: ###

       n = int(input())

  - This line reads an integer from standard input (input()) and converts it to an integer using int().

  - For example, if the user inputs 5, n will be assigned the value 5.

- ### Loop through the Range: ###

       for i in range(1, n + 1):

- This for loop iterates over the range from 1 to n (inclusive). The range(1, n + 1) generates numbers starting from 1 up to and including n.

- In our example, if n is 5, the loop will run with i taking values 1, 2, 3, 4, and 5.

- ### Printing the Values: ###

       print(i, end='')

- The print() function is used to print the current value of i.

- The end='' argument specifies that the printed values should not have a newline character at the end (which is the default behavior of print()). Instead, it uses an empty string, meaning the values are printed on the same line consecutively.

- As the loop iterates, print(i, end='') will output 12345 for the input 5.

## Key Points ##

- range(1, n + 1): Generates a sequence of numbers starting from 1 to n.

- end='': Ensures that the printed values appear on the same line without any spaces in between.

This code efficiently solves the problem by leveraging the for loop and the custom end parameter in the print function to achieve the desired output.
