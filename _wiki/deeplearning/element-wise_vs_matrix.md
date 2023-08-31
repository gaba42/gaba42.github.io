---
layout  : wiki
title   : element-wise vs matrix multiplication
summary : np.dot()과 '*'의 차이
date    : 2023-08-30 17:51:26 +0900
updated : 2023-08-31 10:19:02 +0900
tag     : 
toc     : true
public  : true
parent  : [[/deeplearning]]
latex   : false
---
* TOC
{:toc}

## "*" 연산

- '*' 연산자는 element-wise(요소별 연산)을 수행한다.
- a[i][j] * b[i][j]

```python
# 2D array a와 b
a = [[1, 2], [3, 4]]
b = [[1, 2], [3, 4]]

# output:
[[1, 4]
[9, 16]]
```

아래와 같은 형태가 된다.  
![image](https://github.com/gaba42/gaba42.github.io/assets/106816837/ae0023f4-0e9a-4c50-b809-5a6e2bb9c750)


## np.dot() 연산
- matrix multiplication(행렬곱셈)을 수행한다.
- matrix(행렬) A의 row(행) 개수와 matrix B의 column(열) 개수가 같아야 한다.
	- 아닐시 에러 

## illustration
![image](https://github.com/gaba42/gaba42.github.io/assets/106816837/9ec056a2-7f22-4c68-b192-b386a6481271)

![image](https://github.com/gaba42/gaba42.github.io/assets/106816837/e1b8ce00-01e8-466b-84b4-935d1ca64d12)

# 참고 링크
- [matrix multiplication live demo](http://matrixmultiplication.xyz/)
