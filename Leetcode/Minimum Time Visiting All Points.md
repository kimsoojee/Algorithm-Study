## 🚨 문제
Minimum Time Visiting All Points https://leetcode.com/problems/minimum-time-visiting-all-points/

## 🧩 코드

```python
class Solution(object):
    def minTimeToVisitAllPoints(self, points):
        """
        :type points: List[List[int]]
        :rtype: int
        """
        output = 0
        for i in range(1,len(points)):
            prev = points[i-1]
            curr = points[i]
            output += max(abs(curr[0]-prev[0]), abs(curr[1]-prev[1]))
        return output
```

## 🗣 풀이
```
- prev 포인트와 curr 포인트의 x,y 값끼리의 차가 포인트의 이동수를 나타내기 때문에 이를 비교해서 큰 숫자를 output 에 더해준다.
```
