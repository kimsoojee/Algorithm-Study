## 🚨 문제
Fruit Into Baskets https://leetcode.com/problems/fruit-into-baskets/

## 🧩 코드

```python
class Solution(object):
    def totalFruit(self, tree):
        """
        :type tree: List[int]
        :rtype: int
        """
        
        max_total = 0
        baskets = []
        for f in tree:
            if f in baskets or len(set(baskets)) < 2:
                baskets.append(f)
            else:
                max_total = max(max_total, len(baskets))
                p = len(baskets)-2
                while p > 0:
                    if len(set(baskets[p:])) == 2:
                        break
                    p -= 1
                baskets = baskets[p+1:]+[f]
        max_total = max(max_total, len(baskets))
        return max_total
```

## 🗣 풀이
```
- tree 를 iterate 했을 때 
  만약 바구니에 같은 종류의 과일이 담겨있거나 2가지 이하의 종류의 과일이 담겨있다면 바구니에 과일을 넣는다.
  만약 2개의 종류의 과일이 담긴 상태에서 새로운 과일이 나온다면 이전의 수와 바구니의 갯수를 비교하여 max_total 에 제일 큰 수를 지정해준다.
  그리고 point와 while을 이용하여 이전에 담긴 한가지 종류의 과일을 빼준다.
- 이 방법을 계속 반복하여서 iterate 가 끝났을 때 max_total을 리턴해준다.
```
