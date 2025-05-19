# EX 4C DYNAMIC PROGRAMMING – 3
## DATE: 8.4.25
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm
1. Reverse the input string to create s2, and compare it with the original string s1.

2. Initialize a 2D DP table with -1 to store intermediate results.

3. If characters match, recursively add 1 to the result of the remaining substrings.

4. If characters don’t match, take the maximum of two recursive calls by excluding one character from either string.

5. Return the result stored in the DP table, which gives the length of the LPS.
   

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by: LISIANA T
Register Number: 212222240053
*/
dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))
```

## Output:

![image](https://github.com/user-attachments/assets/a7945873-c89d-4a9a-939c-42cb2884f404)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
