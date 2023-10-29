---
layout  : wiki
title   : 프로그래머스 level 1
summary : 
date    : 2023-10-13 13:27:06 +0900
updated : 2023-10-29 10:22:37 +0900
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


## [크기가 작은 부분 문자열](https://school.programmers.co.kr/learn/courses/30/lessons/147355)
![문제설명](https://github.com/gaba42/gaba42.github.io/assets/106816837/287c214f-7ce3-4b8e-a06b-7f3d2712ff36)
![입출력 예](https://github.com/gaba42/gaba42.github.io/assets/106816837/26050c68-317c-40bd-a32b-97432d9ff5ca)
```python
def solution(t, p):
    result = []
    # 7(t의 길이) - 3(p의 길이) + 1 = 5(가능한 조합 개수) 
    for i in range(len(t) - len(p)+1):
        # t[0+4] 슬라이싱 해서 result에 추가
        result.append(t[i:i+len(p)])
    
    cnt = 0
    # result 값들 비교
    for num in result:
        # p 보다 작거나 같으면
        if num <= p:
            # cnt 1씩 증가
            cnt += 1
    return cnt
```


## [삼총사](https://school.programmers.co.kr/learn/courses/30/lessons/131705)
![문제설명](https://github.com/gaba42/gaba42.github.io/assets/106816837/dfa8aa88-8c52-4f02-b6ba-1167dbe5c0f7)
![입출력 예](https://github.com/gaba42/gaba42.github.io/assets/106816837/cefbc84f-3cdf-44ef-80b9-0dda42d183d3)

```python
from itertools import combinations

def solution(number):
    cnt = 0
    # 입력시 넘겨받은 리스트의 가능한 모든 조합
    comb = list(combinations(number, 3))
    for i in comb:
        # 조합들의 값이 0과 같다면 cnt 1 증가
        if sum(i) == 0:
            cnt += 1
    return cnt
```
"python combination"을 googling 했더니  combinations라는 모듈을 알게 되었다.
이름도 사용하는 방식도 직관적.


## [최소 직사각형](https://school.programmers.co.kr/learn/courses/30/lessons/86491)
![문제설명](https://github.com/gaba42/gaba42.github.io/assets/106816837/2ed43d3f-77f3-4023-b021-e6ceea3430bc)
![입출력 예](https://github.com/gaba42/gaba42.github.io/assets/106816837/489dcf44-ed4b-4d68-9c22-1e059ece4433)

```python
def solutino(sizes):
    re_sizes = [sorted(pair) for pair in sizes]
    size_x = max([pair[0] for pair in re_sizes])
    size_y = max([pair[1] for pair in re_sizes])
    
    ans = size_x * size_y
    return ans
```
좀 더 효율적인 방식으로 짤 수 있을 것 같았는데 역시나.

```python
def solution(sizes):
    return max(max(x) for x in sizes) * max(min(x) for x in sizes)
```
둘 중 큰 수 중 가장 큰 수 * 둘 중 작은 수 중 가장 큰 수  
위 방식으로 계산을 끝내버려서 내가 한 방식보다 훨씬 더 간결하고 이해하기도 쉽다.


## [시저 암호](https://school.programmers.co.kr/learn/courses/30/lessons/12926)
[문제설명](https://github.com/gaba42/gaba42.github.io/assets/106816837/da22b31f-7744-4961-a600-e76e893e2663)
[입출력 예시](https://github.com/gaba42/gaba42.github.io/assets/106816837/9f08e961-cbdf-4738-90a6-3424749ec717)

```python
def solution(s, n):
    ans = ''
    for char in s:
        if char.isalpha():
            ascii_num = ord('a') if char.islower() else ord('A')
            ans += chr((ord(char) - ascii_num + n) % 26 + ascii_num)
        else:
            ans += char
    return ans
```
- 공백이나 숫자는 건드리지 않기 위해 isalpha() 사용해 1차 거른다.
- 아스키 코드값과 아스키 문자로 변환해주는 함수를 사용해 불필요한 리스트를 만들지 않도록 했다.
- 알파벳의 총 길이 26을 넘기지 않도록 modulo 사용해 확인

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
- 1021 : 1  79460 (7만대 진입)
- 1022 : 1  77574
- 1023 : 1  74121
- 1024 : 1  69194 (6만대 진입)
- 1025 : 1  67223
- 1026 : 1  66600
- 1027 : 1  66366
- 1028 : 1  63542
- 1029 : 
