# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
1. Initialize a 2D table (lookup) of size (m+1) x (n+1) with all values set to 0, where m and n are the lengths of strings X and Y.

2. Set maxLength = 0 and endingIndex = m to keep track of the longest match found and where it ends in X.

3. Iterate through both strings: for each X[i-1] and Y[j-1], if they match, set lookup[i][j] = lookup[i-1][j-1] + 1.

4. Update maxLength and endingIndex whenever a longer match is found.

5. Return the substring of X from endingIndex - maxLength to endingIndex as the longest common substring.
   
## Program:
```
/*
Program to implement the longest common substring problem

.
Developed by: LISIANA T
Register Number: 212222240053 
*/
def LCS(X, Y, m, n):
 
    maxLength = 0           
    endingIndex = m         
 
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
 
    for i in range(1, m + 1):
        for j in range(1, n + 1):
 
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
 
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
 
    return X[endingIndex - maxLength: endingIndex]
 
if __name__ == '__main__':
 
    X = input()
    Y = input()
 
    m = len(X)
    n = len(Y)
    
    print('The longest common substring is', LCS(X, Y, m, n))
```

## Output:

![image](https://github.com/user-attachments/assets/46bbc094-346a-43d9-ae23-f55188b470d8)


## Result:
Thus the program was executed successfully for finding the longest common substring .
