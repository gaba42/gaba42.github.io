---
layout  : wiki
title   : rebase
summary : commit 내역은 지우되 code 내용은 현재 상태에 두는 방법
date    : 2023-08-31 10:38:16 +0900
updated : 2023-08-31 10:46:56 +0900
tag     : git rebase commit
toc     : true
public  : true
parent  : [[/git]]
latex   : false
---
* TOC
{:toc}

민감한 정보가 노출된 상태로 계속 커밋을 해온 걸 확인하면 참으로 난감하다. 하나씩 수정할 수도 없고......  
구글링의 결과:  rebase

.git 폴더를 삭제하면 내 git repo에 문제가 생길수도 있다.  
다음 방법을 따라하면 안전하게 원하는 결과를 얻을 수 있다.

1. Checkout
	- `git checkout --orphan <branch_name>`
2. 파일 추가
	- `git add -A`
3. 변경 사항 커밋
	- `git commit -am "commit message"`
4. 브랜치 삭제
	- `git branch -D master`
5. 현재 브랜치를 master 브랜치로 이름 변경
	- `git branch -m master`
6. repo 강제 업데이트
	- `git push -f origin main`

# 참고 링크
- [how to delete all commit history in github](https://stackoverflow.com/questions/13716658/how-to-delete-all-commit-history-in-github)

