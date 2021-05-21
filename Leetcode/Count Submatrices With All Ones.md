## 🚨 문제
Count Submatrices With All Ones https://leetcode.com/problems/count-submatrices-with-all-ones

## 🧩 코드

```python
class Solution(object):
    def numSubmat(self, mat):
        rectangles = 0
        for x in range(len(mat)):
            for y in range(len(mat[0])):
                if mat[x][y] == 1:
                    rectangles+=1
                    r = y+1
                    while r < len(mat[0]):
                        if mat[x][r] == 0:
                            break
                        rectangles+=1
                        s = x+1
                        while s < len(mat):
                            if sum(mat[s][y:r+1]) != r-y+1:
                                break
                            rectangles += 1
                            s += 1
                        r+=1
                    d = x+1
                    while d < len(mat):
                        if mat[d][y] == 0:
                            break
                        rectangles+=1
                        d+=1
        return rectangles
```

## 🗣 풀이
```
- 만약 mat[x][y]의 숫자가 1일때 rectangle의 갯수 +1 을 해주고,
  - while 을 이용하여 y의 위치에서 1xr 사이즈의 사각형의 갯수를 구한다.
    - while과 1xr의 사이즈를 이용하여 sxr의 사이즈의 사각형의 갯수를 구한다.
  - while을 이용하여 x의 위치에서 dx1 사이즈의 사각형의 갯수를 구한다.
```

## 📚 다른 사람의 풀이

```python
class Solution(object):
    def numSubmat(self, mat):
        m = len(mat)
        n = len(mat[0])
        dp = [[0] * n for _ in range(m)]
        for i in range(m):
            for j in range(n):
                if i == 0 and mat[i][j]:
                    dp[i][j] = 1
                elif mat[i][j]:
                    dp[i][j] = dp[i-1][j] + 1
        total = 0
        for i in range(m):
            for j in range(n):
                for k in range(j+1, n+1):
                    total += min(dp[i][j:k])
        return total
```
