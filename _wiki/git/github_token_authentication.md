---
layout  : wiki
title   : github authentication 에러
summary : github token 
date    : 2023-12-08 10:40:21 +0900
updated : 2023-12-08 11:33:28 +0900
tag     : github authentication token 인증
resource: 8E/3B09D3-F530-46C1-B31F-FA74B1433032
toc     : true
public  : true
parent  : [[/git]]
latex   : false
---
* TOC
{:toc}

## authentication error
<img width="447" alt="github authentication error screenshot" src="https://github.com/gaba42/gaba42.github.io/assets/106816837/fc1f5042-4c92-4fcc-b9c6-2356373779bc">

여느 때처럼 git push 후 위와 같은 에러를 보게 된다면 십중팔구는 깃허브 토큰이 만료된 경우다. 
- 깃허브 비밀번호 인증은 2021년 8월 13일 이후로 지원하지 않고 있다.


다음과 같은 순서로 해결이 가능하다.
1. 깃허브 토큰 발급
2. 이전 깃허브 관련 credential 삭제
3. 1번에서 발급 받은 토큰을 사용해 연결

## 깃허브 토큰 발급
- **깃허브 사이트에서 로그인 후 우측 상단 프로필 사진 클릭 -> Settings 클릭**
<img width="281" alt="github settings" src="https://github.com/gaba42/gaba42.github.io/assets/106816837/b6b99667-2f8a-40b7-a4ae-d956686469a1">  
거의 아래에 위치해 있다.  
<br>


- **Developer Settings 클릭**  
<img width="290" alt="Developer Settings" src="https://github.com/gaba42/gaba42.github.io/assets/106816837/fa142522-bb32-4a3f-8086-4242cf5b0ebb">  
제일 아래에 위치해 있다.  
<br>

- **Personal access tokens -> Tokens (classic) -> Generate new token(classic)**
<img width="529" alt="Generate new token" src="https://github.com/gaba42/gaba42.github.io/assets/106816837/79319670-659c-4ed1-b8b7-f8cd953f04e0">  
만료기한과 권한 설정 후 맨 아래에 있는 초록색의 [Generate token] 클릭

<br>


- **토큰 복사**  
Generate token 클릭 후 새로 생성된 토큰을 볼 수 있는데, 딱 이 때만 볼 수 있다. 그러니 꼭 복사해서 안전하게 저장할 것.


## 토큰 사용
- **터미널에서 해당 github repository로 이동 후 아래 명령어 입력**
```
git remote set-url origin https://[token]@github.com/[git_repo]
```
<br>

**git_repo**
- 해당 레포의 주소 뒷부분
- 예시) https://github.com/gaba42/gaba42.github.io
- [token]@github.com/gaba42/gaba42.github.io

# 참고
- [GitHub Docs](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)
