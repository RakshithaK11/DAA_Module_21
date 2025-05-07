# EX 3B Hamiltonian Circuit Problem
## DATE:
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1.Import required module:
from itertools import permutations

2.Get all nodes of the graph:
nodes = list(graph.keys())

3.Generate all permutations of nodes:
paths = permutations(nodes)

4.Check each path for Hamiltonian validity:
for path in paths:

5.Verify if consecutive nodes are connected in graph:
if all(path[i+1] in graph[path[i]] for i in range(len(path)-1)): print("Hamiltonian Path Exists"); break 

## Program:
~~~
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: RAKSHITHA K
Register Number:  212223110039

def Hamiltonian_path(adj, N):
    ######################### Add your Code here ##########################
    #Start here
    dp = [[False for i in range(1 << N)] for j in range(N)]
    for i in range(N):
        dp[i][1 << i] = True
    for i in range(1 << N):
        for j in range(N):
            if ((i & (1 << j)) != 0):
 
                for k in range(N):
                    if ((i & (1 << k)) != 0 and
                             adj[k][j] == 1 and
                                     j != k and
                          dp[k][i ^ (1 << j)]):
                        dp[j][i] = True
                        break
    for i in range(N):
        if (dp[i][(1 << N) - 1]):
            return True
    return False
    #End here
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
~~~

## Output:
![image](https://github.com/user-attachments/assets/1857c50f-be04-440b-aeae-eea8e543ae25)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
