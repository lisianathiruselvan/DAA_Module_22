# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
1. Initialize a 2D matrix of size (m+1)×(n+1) with all values set to 0, where m and n are lengths of the two strings.

2. Iterate through each character of both strings using two nested loops.

3. If characters match, set matrix[i][j] = 1 + matrix[i-1][j-1].

4. If characters don’t match, set matrix[i][j] = max(matrix[i-1][j], matrix[i][j-1]).

5. Return the value in the bottom-right cell of the matrix as the length of the LCS.
   

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: LISIANA T
Register Number:  212222240053
*/
def lcs(str1 , str2):
    m = len(str1)
    n = len(str2)
    matrix = [[0]*(n+1) for i in range(m+1)] 
    for i in range(m+1):
        for j in range(n+1):
            if i==0 or j==0:
                matrix[i][j] = 0
            elif str1[i-1] == str2[j-1]:
                matrix[i][j] = 1 + matrix[i-1][j-1]
            else:
                matrix[i][j] = max(matrix[i-1][j] , matrix[i][j-1])
    return matrix[-1][-1]
str1 = input()
str2 = input()
lcs_length = lcs(str1, str2)
print("Length of LCS is : {}".format(lcs_length))
```

## Output:

![image](https://github.com/user-attachments/assets/22c8e5da-c011-4e60-b619-54b628a1daa5)



## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
