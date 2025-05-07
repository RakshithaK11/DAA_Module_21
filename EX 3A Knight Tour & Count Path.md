# EX 3A Knight Tour & Count Path
## DATE:
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1.Define knight moves:
moves = [(2,1),(1,2),(-1,2),(-2,1),(-2,-1),(-1,-2),(1,-2),(2,-1)]

2.Initialize queue with start position and steps = 0:
q = deque([(start_x, start_y, 0)])

3.Track visited positions:
visited = set([(start_x, start_y)])

4.Run BFS loop:
while q: x, y, steps = q.popleft()

5.Check target or add valid next moves:
if (x, y) == (end_x, end_y): print(steps); break; [q.append((nx, ny, steps+1)) or visited.add((nx, ny)) for dx, dy in moves if 0 <= (nx:=x+dx) < N and 0 <= (ny:=y+dy) < N and (nx, ny) not in visited]

## Program:
~~~
Developed by: RAKSHITHA K
Register no: 212223110039
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
     
    # add your code here
    #Start here
    dx = [2, 2, -2, -2, 1, 1, -1, -1]
    dy = [1, -1, 1, -1, 2, -2, 2, -2]
    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited = [[False for i in range(N + 1)] for j in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True
    while(len(queue) > 0):
        t = queue[0]
        queue.pop(0)
        if(t.x == targetpos[0] and
           t.y == targetpos[1]):
            return t.dist
        for i in range(8):
            x = t.x + dx[i]
            y = t.y + dy[i]
            if(isInside(x, y, N) and not visited[x][y]):
                visited[x][y] = True
                queue.append(cell(x, y, t.dist + 1))
    #End here
    
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
 ~~~

## Output:
![image](https://github.com/user-attachments/assets/b37c5819-af83-4e93-b1fe-a9dfc522bcc3)

## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
