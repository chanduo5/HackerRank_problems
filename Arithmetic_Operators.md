# Problem Description #

Your task is to read two integers from the standard input, perform three operations on these integers, and print the results:

- Calculate and print the sum of the two integers.

- Calculate and print the difference between the two integers (subtract the second integer from the first).

- Calculate and print the product of the two integers.



## Example ##

If the input integers are 5 and 3, the output should be:

8
2
15

Explanation:
- Sum: 5 + 3 = 8

- Difference: 5 - 3 = 2

- Product: 5 * 3 = 15

## Input Format ##

The input consists of two integers:

- The first integer, a.

- The second integer, b.

### Code Implementation ###

Here's the Python code that accomplishes this task:
python

    if __name__ == '__main__':
        a = int(input("first integer a:"))
        b = int(input("second integer b:"))
    
    # Calculate the sum of the two numbers
        sum_result = a + b
    
    # Calculate the difference between the two numbers
        difference_result = a - b
    
    # Calculate the product of the two numbers
       product_result = a * b
    
    # Print the results
       print(sum_result)
       print(difference_result)
       print(product_result)

## Explanation of the Code ##

- Reading Input: The input() function reads the input from the standard input (usually the keyboard). In this code, it reads two integers, a and b.

- Calculating Results:

    The sum of the two integers is calculated and stored in the variable sum_result.

    The difference (first integer minus the second integer) is calculated and stored in the variable difference_result.

    The product of the two integers is calculated and stored in the variable product_result.

- Printing Results: The print() function prints the calculated results, each on a new line.
