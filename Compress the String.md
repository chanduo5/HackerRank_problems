# Problem Description #

You are given a string 𝑆 consisting of digits from 0 to 9. Your task is to replace consecutive occurrences of any character in the string with a tuple (𝑋,𝑐), where 𝑋 is the count of consecutive occurrences and 𝑐 is the character itself.

### Input Format: ###
- A single line of input consisting of the string 𝑆.

### Output Format: ###
- A single line of output consisting of the modified string.

### Constraints: ###
- All the characters of 𝑆 denote integers between 0 and 9.

- 1 ≤∣ 𝑆 ∣ ≤ 10⁴

## Sample Input: ##
1222311

## Sample Output: ##
(1, 1) (3, 2) (1, 3) (2, 1)

## Explanation: ##

- The character '1' occurs only once. It is replaced by (1, 1).

- The character '2' occurs three times consecutively. It is replaced by (3, 2).

- The character '3' occurs only once. It is replaced by (1, 3).

- The character '1' occurs twice consecutively. It is replaced by (2, 1).

## Solution Code: ##
Here’s the Python code to solve this problem using the groupby function from the itertools module:
python


    from itertools import groupby

    def compress_string(s):
       result = []
       for key, group in groupby(s):
           count = len(list(group))
           result.append(f"({count}, {key})")
    return ' '.join(result)

    # Sample Input
      s = "1222311"

    # Output
    print(compress_string(s))

This code will take a string 𝑠 and use the groupby function to group consecutive characters. For each group, it will count the number of occurrences and format them as (𝑋,𝑐), where 𝑋 is the count and 𝑐 is the character. The result will be a single string with the modified content, separated by spaces.
