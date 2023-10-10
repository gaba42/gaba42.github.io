---
layout  : wiki
title   : stable diffusion을 사용해 착시현상 사진 만들기
summary : 
date    : 2023-10-06 00:04:14 +0900
updated : 2023-10-06 08:16:46 +0900
tag     : generative ai stable diffusion controlnet
toc     : true
public  : true
parent  : [[/projects]]
latex   : false
---
* TOC
{:toc}

# 순서
1. stable diffusion software/A1111 UI 설치
2. 이미지 생성을 위한 stable diffusion 모델(checkpoint) 설치
	- CIVIT.AI
3. controlnet extension 설치
	- sd-webui-controlnet
4. controlnet 모델 설치


# Automatic 1111
stable diffusion용 UI 중 가장 인기많은 automatic1111을 우선 설치하자.

- [automatic1111 github](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
github 페이지에 들어가면 내용이 많아 복잡해보일 수 있으나, 이럴 때는 installation이라 부분만 찾으면 된다.

## prerequisite
- [python](https://www.python.org/downloads/release/python-3106/)
- [git](https://git-scm.com/download/win)

## automatic 1111 설치
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
- NaNs exception => python version 문제로 예상
	- python 11.4 => python 10.6으로 변경하고 재시도 


## stable diffusion으로 좋은 결과물을 생성하려면
1. 좋은 모델(checkpoint 파일)
2. 좋은 프롬프

## 추가사항
**Settings**
- Live previews -> Live preview display period > 0
	- 0 또는 -1로 설정을 하면 전부 다 만들어지고 나서만 보인다. 

**Extensions**
- aspect ratio selector 
	- 비율 조정  
- sd-webui-controlnet manipulations
	- stable diffusion automatic 1111을 위한 아주 강력한 extension. star수도 압도적으로 많다   
- canvas zoom UI related
	- 사진을 zoom in/zoom out 하게 해준다
	- 사진 inpainting(재구성)시 유용하다
