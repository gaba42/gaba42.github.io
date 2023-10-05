---
layout  : wiki
title   : stable diffusion을 사용해 착시현상 사진 만들기
summary : 
date    : 2023-10-06 00:04:14 +0900
updated : 2023-10-06 00:40:55 +0900
tag     : generative ai stable diffusion controlnet
toc     : true
public  : true
parent  : [[/projects]]
latex   : false
---
* TOC
{:toc}

# Automatic 1111
stable diffusion용 UI 중 가장 인기많은 automatic1111을 우선 설치하자.

- [automatic1111 github](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
github 페이지에 들어가면 내용이 많아 복잡해보일 수 있으나, 이럴 때는 installation이라 부분만 찾으면 된다.

231005
- git clone 통해 automatic 1111 설치 완료
- webui-user 파일 변경
	- xformers, autolaunch, medvram 적용
- civit.ai
	- DreamShaper 모델 다운로드
	- webui-user 실행시켜 torch, torchvision 등등 다운로드

Stable Diffusion을 사용할 수 있습니다!


## automatic 1111 update
가끔 업데이트를 해줄 필요가 있다.
1. stable-diffusion-webui 위치에서 cmd 실행
2. git pull
3. 끝

## error
- NaNs exception
