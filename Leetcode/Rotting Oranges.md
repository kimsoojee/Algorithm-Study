## 🚨 문제
Rotting Oranges https://leetcode.com/problems/rotting-oranges/

## 🧩 코드

```python
class Solution(object):
    def orangesRotting(self, grid):
        rotten = []
        fresh = 0
        for x in range(len(grid)):
            for y in range(len(grid[0])):
                if grid[x][y]==2:
                    rotten.append([x,y])
                elif grid[x][y]==1:
                    fresh+=1
        
        if fresh == 0:
            return 0
        
        direction = [[-1,0],[1,0],[0,-1],[0,1]]
        minutes = 0
        
        while rotten:
            size = len(rotten)
            for l in range(size):
                orange = rotten.pop(0)
                orange_r = orange[0]
                orange_c = orange[1]
                for i,j in direction:
                    nr = orange_r+i
                    nc = orange_c+j
                    if nr>=0 and nr<len(grid) and nc>=0 and nc<len(grid[0]):
                        if grid[nr][nc] == 1:
                            grid[nr][nc] = 2
                            rotten.append([nr,nc])
                            fresh -= 1
            minutes += 1
            
        if fresh != 0:
            return -1
        else:
            return minutes-1
```

## 🗣 풀이
```
- for loop 을 이용하여 썩은 오랜지의 위치를 rotten list 에 저장하고 fresh orange 의 갯수를 센다.
- 만약 fresh orange 의 갯수가 0 이라면 0분이 걸리기 때문에 0 을 리턴해준다.
- direction 은 양옆, 위, 아래의 오렌지를 체크하기 위해 쓰인다.
- while 을 이용하여 grid 안에 있는 모든 오렌지를 체크하고 오렌지가 모두 썩으면 stop 해준다.
  - for loop 을 이용하여 같은 시간대의 오렌지들을 체크해준다.
    - rotten 안에 있는 썩은 오렌지들의 위치를 direction 을 이용하여 양옆, 위, 아래의 오랜지들을 체크하는데 숫자가 1이면 2로 바꿔주고 rotten list 에 추가해준다.
- 만약 모든 오랜지가 다 썩지 않았다면 -1, 오렌지가 모두 썩었다면 minutes-1 을 리턴해준다.
```
