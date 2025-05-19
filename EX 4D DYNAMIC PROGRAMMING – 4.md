# EX 4D DYNAMIC PROGRAMMING – 4
## DATE: 12.4.25
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.





## Algorithm
1. If one string is empty, return the length of the other (all insertions or deletions).

2. If last characters match, no cost is added; else, set cost = 1.

3. Recursively compute the minimum cost of three operations: insert, delete, and replace.

4. Take the minimum of the three recursive results, adding the corresponding operation cost.

5. Return the result, which represents the minimum number of edits to convert one string into another.

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: LISIANA T
Register Number: 212222240053  
*/
def LD(s, t):
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1,
               LD(s, t[:-1])+1, 
               LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))


```

## Output:

![image](https://github.com/user-attachments/assets/27021a93-545b-4864-b983-2d0d4bd18697)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
