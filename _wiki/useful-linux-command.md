---
layout  : wiki
title   : 알아두면 유용한 리눅스 명령어
summary : 
date    : 2023-10-10 13:47:18 +0900
updated : 2023-10-10 13:49:57 +0900
tag     : linux
toc     : true
public  : true
parent  : [[/index]]
latex   : false
---
* TOC
{:toc}

# 서버 운용이 유용한 리눅스 명령어
- 먼저 FTP로 파일 옮기기
 
```linux
conda env list
conda activate <가상환경>
export PYTHONPATH=$PYTHONPATH:<프로젝트 위치>
cd <실행파일 위치>

nohup python -u 실행파일.py
로그.out
&
tailf 로그.out(나가기: ctrl+z)

ps -ef|grep python
kill -9 <죽이고 싶은 프로세스 넘버>

watch -n 1 nvidia-smi
```
