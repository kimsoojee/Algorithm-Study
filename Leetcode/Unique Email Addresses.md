## 🚨 문제
Unique Email Addresses https://leetcode.com/problems/unique-email-addresses/

## 🧩 코드

```python
class Solution(object):
    def numUniqueEmails(self, emails):
        """
        :type emails: List[str]
        :rtype: int
        """
        
        for x in range(len(emails)):
            seperate = emails[x].split('@')
            index_plus = seperate[0].find('+')
            if index_plus != -1:
                seperate[0] = seperate[0][:index_plus]
            seperate[0] = seperate[0].replace('.','')
            emails[x] = seperate[0]+'@'+seperate[1]
        return len(set(emails))
```

## 🗣 풀이
```
- for loop 을 이용하여 각 이메일 주소를 체크한다.
- for loop 안에 '@' 로 split 해주어 seperate 이라는 리스트안에 local name 과 domain name 으로 분리해준다.
- 만약 local name 에 '+' 가 있는지 확인하고, 있다면 '+' 를 포함하여 그 뒤에 스트링을 없애주도록 한다.
- local name 에 '.'가 있다면 replace 를 이용하여 없애준다.
- email 주소를 local name + '@' + domain 으로 다시 이어준다.
- loop 이 끝나고 이메일 리스트에 반복되는 이메일을 없애주기위해 set 으로 변경해주고 그 길이를 return 해준다.
```

