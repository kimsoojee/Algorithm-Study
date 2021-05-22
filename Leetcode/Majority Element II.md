## 🚨 문제
Majority Element II https://leetcode.com/problems/majority-element-ii

## 🧩 코드

```python
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        import math
        from collections import defaultdict
        answer = []
        count = math.floor(len(nums)/3)
        table = defaultdict(int)
        for x in nums:
            table[x] += 1
        for k,v in table.items():
            if v > count:
                answer.append(k)
        return answer
```

## 🗣 풀이
```
- table 을 이용하여 nums 안에 있는 숫자의 갯수를 저장한다.
- table 의 key와 value를 iterate 하며 value의 숫자가 count보다 크다면 answer에 추가해준다.
```
