## 🚨 문제
Invalid Transactions https://leetcode.com/problems/invalid-transactions

## 🧩 코드

```python
class Solution(object):
    def invalidTransactions(self, transactions):
        """
        :type transactions: List[str]
        :rtype: List[str]
        """
        from collections import defaultdict
        table = defaultdict(list)
        invalid = []
        for x in transactions:
            sp = x.split(",")
            table[sp[0]].append(sp)
        
        for k,v in table.items():
            for i in range(len(v)):
                if int(v[i][2]) > 1000:
                    invalid.append(",".join(v[i]))
                else:
                    for j in range(len(v)):
                        if i == j:
                            continue
                        if abs(int(v[i][1])-int(v[j][1])) <= 60 and v[i][3]!=v[j][3]:
                            invalid.append(",".join(v[i]))
                            break
        return invalid
```

## 🗣 풀이
```
- table dictionary 에 같은 이름의 transaction 을 분류한다.
- table 에 담긴 transaction 끼리 for loop 을 이용하여 서로 비교한다.
  - 만약 transaction 의 금액이 1000 을 넘어간다면 invalid에 추가한다.
  - 1000이 넘지 않는다면 다른 transaction들과 비교하여 60분 안에 다른 도시에서 transaction 이 있다면 invalid 에 추가해준다.
```
