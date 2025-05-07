# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1.Set i = 0 to start checking from the beginning of the text.

2.For each i, compare pattern characters with text starting at position i.

3.If all characters match, return the current index i as the match position.

4.If any character does not match, move to the next index i + 1.

5.Repeat until the end of the text; if no match is found, return -1.
## Program:
~~~
Program to implement the Pattern Matching.
Developed by: RAKSHITHA K
Register Number:  212223110039

def BF(s1,s2):
##############  Add your code here #############
 #Start here
    i = 0
    j = 0
    while(i < len(s1) and j < len(s2)):
        if(s1[i] ==  s2[j]):
            i += 1
            j += 1
        else:
            i = i - j + 1
            j = 0
    if(j >= len(s2)):
        return i - len(s2)
    else:
        return 0
    #End here
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

~~~

## Output:
![image](https://github.com/user-attachments/assets/17296da4-e445-4ab1-b762-b45468f4bff3)

## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
