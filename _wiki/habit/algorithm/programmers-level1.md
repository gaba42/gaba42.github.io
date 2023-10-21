---
layout  : wiki
title   : 프로그래머스 level 1
summary : 
date    : 2023-10-13 13:27:06 +0900
updated : 2023-10-21 22:07:36 +0900
tag     : programmers algorithm
resource: B2/CDD069-F383-48AC-B1F3-3A3517E4EC1E
toc     : true
public  : true
parent  : [[/habit/algorithm/programmers]]
latex   : false
---
* TOC
{:toc}

# 프로그래머스 level 1 풀이

레벨 1 정답률이 높은 순으로 풀고 있다. 231012 기준 python3, lv1의 문제 개수는 총 77개. [나머지가 1이 되는 수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/87389)와 [평균 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/12944)는 이미 풀었으므로 최대 75개만 이 페이지에 올라올 예정이다.

## [약수의 합](https://school.programmers.co.kr/learn/courses/30/lessons/12928)
**문제 설명**  
정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수

**입출력 예**

| n  | return |
|----|--------|
| 12 | 28     |
| 5  | 6      |

입출력 예 #1
12의 약수는 1, 2, 3, 4, 6, 12입니다. 이를 모두 더하면 28입니다.

입출력 예 #2
5의 약수는 1, 5 입니다. 이를 모두 더하면 6 입니다. 

```python
# 내 풀이
def solution(n):
    answer = sum([x for x in range(1, x+1) if n%x==0])
    return answer

# num / 2의 수들만 검사해 속도 향상
def solution(num):
    return num + sum([i for i in range(1, (num // 2) + 1) if num % i == 0])
    
# 단순히 문제 풀이만 한 것이 아니라 속도 개선까지 생각했다.
```

## [짝수와 홀수](https://school.programmers.co.kr/learn/courses/30/lessons/12937)
**문제 설명**  
정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수.

**제한 조건**  
num은 int 범위의 정수입니다.  
0은 짝수입니다.

**입출력 예**

| num | return |
|-----|--------|
| 3   | 'Odd'  |
| 4   | 'Even' |

```python
# 내 풀이
def solution(num):
    if num % 2 == 0:
        answer = 'Even'
    else:
        answer = 'Odd'
    return answer
    
# 실행 순서 (num % 2 and 'Odd') or 'Even'
def evenOrOdd(num):
    if num%2:
        return 'Odd'
    return 'Even'

# 이렇게 나머지가 있느냐 없느냐로 코드를 짧게 작성한 분도 계신다.
```

## 문자열 내 p와 y의 개수
**문제 설명**  
대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

**제한사항**
- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.

**입출력 예**

| s         | answer |
|-----------|--------|
| "pPoooyY" | true   |
| "Pyy"     | false  |

```python
# 내 풀이
def solution(s):
    answer = True
    
    # [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
    s = s.lower()
    p1 = 0
    y1 = 0
    res = [x for x in s if x == 'p' or x == 'y']
    if len(res) % 2 != 0:
        return False
    else:
        for i in res:
            if i == 'p':
                p1 += 1
            else:
                y1 += 1
        
        if p1 == y1:
            answer=True
        else:
            answer = False
        
    return answer

# count()
def solution(n):
    return s.lower().count('p') == s.lower().count('y')

# Counter
from collections import Counter
def solution(n):
    c = Counter(s.lower())
    return c['p'] == c['y']
    
# return 에서 바로 비교
return a == b
```

내 풀이는 좀더 구구절절인 반면, 다른 사용자들의 풀이는 읽기도 쉽고 훨씬 직관적이다.

## 정수 제곱근 판별

```python
import math
def solution(n):
    answer = 0
    if math.sqrt(n).is_integer():
        return (math.sqrt(n) + 1)**2
    return -1

#  ** (1/2) == sqrt()
def nextSqure(n):
    sqrt = n ** (1/2)

    if sqrt % 1 == 0:
        return (sqrt + 1) ** 2
    return 'no'
    
# **(1/2)이 제곱근!
```
이 문제의 다른 사람 풀이들을 보면서 코드가 짧으면 좋은 코드라는 인식이 있어서인지 무조건 짧게만 작성하려고 하는 듯한 느낌을 받았다.
코딩은 작문이다. 한글로 작문하느냐, 파이썬으로 작문하느냐, 언어의 차이가 있을 뿐. 컴퓨터 언어(computer language)라고 불리는데는 이유가 있다. 

## 

---
- 1012 : 8
- 1013 : 4
- 1014 : 2
- 1015 : 4
- 1016 : 3
- 1017 : 1
- 1018 : 4  83865
- 1019 : 2  83003 (2문제만 풀었는데 800위가 껑충 오르다니.)
- 1020 : 1  80626
- 10201 : 1 79460 (7만대 진입)
