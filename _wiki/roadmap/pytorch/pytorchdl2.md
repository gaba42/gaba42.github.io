---
layout  : wiki
title   : 차근차근 실습하며 배우는 파이토치 딥러닝 프로그래밍
summary : 
date    : 2023-10-03 20:26:55 +0900
updated : 2023-10-03 21:22:59 +0900
tag     : pytorch
resource: D7/ADBA2D-4876-4AE1-8E57-66350B2FBDF5
toc     : true
public  : true
parent  : [[/roadmap/pytorch]]
latex   : false
---
* TOC
{:toc}

## 책을 다 읽고 난 뒤 목적
- 이미지 분류 모델 실습
- 나오는 코드의 모든 해으이 의미 이해 및 필요에 따라 수정까지 할 수 있을 것

## 자료
- [책 깃허브](https://github.com/wikibook/pytorchdl2/blob/master/notebooks.md)
- 딥러닝을 위한 수학

# 딥러닝에 꼭 필요한 파이썬의 개념
```python
# y가 동시에 변하면 안 되는 경우, numpy의 copy 함수를 사용한다
x = np.array([5, 6, 8])
y = x.copy()

# x의 특정 요소 값이 변해도, y에는 영향이 없음
x[1] = -1
print(x)  # [5, -1, 9]
print(y)  # [5, 6, 8]
```

## 1.3 합성 함수
- 수학에서의 합성 함수: 여러 개의 함수를 조합한 함수  
- 딥러닝의 예측 알고리즘: **막대한 파라미터를 가진 복잡한 합성 함수**  

$$ f(x) = 2x^2 + 2 $$를 함수로 정의한다.  
  
$$( a^2 )$$

$ 2x^2 $ 


```python
# 세 가지 기본 함수 정의

def f1(x):
    return(x**2)

def f2(x):
    return(x*2)

def f3(x):
    return(x+2)
    
# 합성 함수 만들기
x1 = f1(x)
x2 = f2(x1)
y = f3(x2)
```
여기서 포인트는 함수 $f1$
