---
layout  : wiki
title   : 밑바닥부터 시작하는 딥러닝 2
summary : 
date    : 2023-10-05 16:16:02 +0900
updated : 2023-10-05 16:56:14 +0900
tag     : 
toc     : true
public  : true
parent  : [[/roadmap]]
latex   : false
---
* TOC
{:toc}

# 3장 word2vec
이번 장에서 배운 내용
- 추론 기반 기법은 추측하는 것이 목적이며, 그 부산물로 단어의 분산 표현을 얻을 수 있다.
- word2vec은 추론 기반 기법이며, 단순한 2층 신경망이다
- word2vec은 skip-gram 모델과 CBOW 모델을 제공한다.
- CBOW 모델은 여러 단어(맥락)로부터 하나의 단어(타깃)를 추측한다.
- 반대로 skip-gram 모델은 하나의 단엉(타깃)로부터 다수의 단어(맥락)를 추측한다.
- word2vec은 가중치를 다시 학습할 수 있으므로, 단어의 분산 표현 갱신이나 새로운 단어 추가를 효율적으로 수행할 수 있다.

# 4장 word2vec 속도 개선
**CBOW 문제점**
- 말뭉치가 커진다 => 계산량도 커진다
  
**개선방법**
1. Embedding(임베딩, 새로운 계층)
2. Negative sampling(네거티브 샘플링, 새로운 손실 함수)

Embedding 
- 단어를 vector로 표현하는 방법
- 자연어를 컴퓨터가 이해할 수 있게 변환하는 작업

Negative Sampling
- softmax 대신 사용하면 어휘가 아무리 많아져도 계산량을 낮은 수준에서 일정하게 억제할 수 있다.
