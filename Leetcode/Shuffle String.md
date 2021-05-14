## 🚨 문제
Shuffle String https://leetcode.com/problems/shuffle-string/

## 🧩 코드

```python
class Solution(object):
    def restoreString(self, s, indices):
        """
        :type s: str
        :type indices: List[int]
        :rtype: str
        """
        s_ind = sorted(zip(indices,s))
        result = ""
        for x,y in s_ind:
            result += y
        return result
```

## 🗣 풀이
```
- s 와 indices 를 zip 을 이용하여 알파벳과 그 위치를 같이 묶어주고, sorted 를 이용하여 순서대로 나열해준다.
- for 루프를 이용하여 순서대로 나열된 알파벳을 result 에 넣어준다.
```
