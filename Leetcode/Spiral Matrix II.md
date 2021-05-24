## 🚨 문제
Spiral Matrix II https://leetcode.com/problems/spiral-matrix-ii/submissions/

## 🧩 코드

```python
class Solution(object):
    def generateMatrix(self, n):
        r,c = 0,0
        direction = [[0,1],[1,0],[0,-1],[-1,0]]
        d = 0
        num = 1
        matrix = [[0]*n for _ in range(n)]
        while num<=n*n:
            matrix[r][c]=num
            num+=1
            row = (r+direction[d][0])%n
            col = (c+direction[d][1])%n
            
            if matrix[row][col]!=0:
                d=(d+1)%4
            r += direction[d][0]
            c += direction[d][1]
        return matrix
```

## 🗣 풀이
```
- (0,0)에서 시작하고 이동방향이 좌,아래,우,위로 반복되기 때문에 direction 에 그 순서대로 넣어준다.
- while loop 을 이용하여 matrix 안에 숫자를 넣어주고 숫자가 n^2 보다 커지면 멈춘다.
  - 만약 다음 순서로 움직였을때 숫자가 0이 아니라면 direction을 이용하여 다른 방향으로 바꿔주고 숫자 넣는 것을 반복한다.
```
