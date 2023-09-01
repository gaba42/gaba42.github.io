---
layout  : wiki
title   : mac으로 컴퓨터 소리와 함께 화면 녹화하기
summary : 
date    : 2023-09-01 21:13:18 +0900
updated : 2023-09-01 22:03:47 +0900
tag     : quicktime blackhole
resource: 04/C15D38-2345-4236-AD3B-AEF441A5B5FE
toc     : true
public  : true
parent  : [[/how-to]]
latex   : false
---
* TOC
{:toc}

mac에 기본적으로 내장되어 있는 quicktime을 사용하면 손쉽게 스크린샷과 녹화를 할 수 있다. 하지만 컴퓨터의 소리는 quicktime으로 녹음하는 게 불가능하다. 다행히도 조금의 세팅만 해주면 된다.

## BlackHole Audio 다운로드

- [download link](https://github.com/ExistentialAudio/BlackHole)  
![image](https://github.com/gaba42/gaba42.github.io/assets/106816837/71989b28-0f01-4c28-bdb6-42f509529278)  
- download installer 클릭   

![blackhole installer](https://github.com/gaba42/gaba42.github.io/assets/106816837/d547ac74-7d3d-40d6-a23b-225921d7ca84)  
- 위의 페이지로 이동이 되고, 기부를 요청하는데 비용을 지불할 의사가 없으면 [I can't afford to pay] 버튼을 클릭  

![info](https://github.com/gaba42/gaba42.github.io/assets/106816837/9c2ead69-49c4-47d9-ac7b-8db2f0eb7111)  
- 누군가에게 오늘 하루 기분 좋은 일 해달라는 산뜻한 문구를 볼 수 있다.
- 다운로드 링크를 받을 이메일 주소, 이름, 성을 적어서 제출
- 이메일 확인  

![blackhole ch16](https://github.com/gaba42/gaba42.github.io/assets/106816837/bc3f1045-70df-410f-907c-0b7346966fdd)  
- BlackHole 16ch 드라이버 선택
- installer 실행시켜 컴퓨터에 드라이버 설치


## Audio MIDI 설정
![Audio MIDI setup](https://github.com/gaba42/gaba42.github.io/assets/106816837/748040c3-f895-4a67-89e3-fcbbfd8942d3)
- 보통 맥의 기타 폴더에서 찾을 수 있다.
- 여기서 input/output aggregate device를 설정한다.

![create aggregate device](https://github.com/gaba42/gaba42.github.io/assets/106816837/c0eed3e3-0244-4bcc-9f49-84079d9d35d3)  
- 하단의 +을 클릭 
- [create aggregate device] 클릭

![blackhole audio input](https://github.com/gaba42/gaba42.github.io/assets/106816837/26d2aa9e-ad3b-4871-96cb-735f58d71f7a)
- BlackHole Audio Input으로 이름 변경
- BlackHole 16ch 선택

![multi output device](https://github.com/gaba42/gaba42.github.io/assets/106816837/113b3e3d-5c1a-49ac-a590-4d3b84043415)
- + 클릭해 하나 더 새로 생성
- 이번에는 [multi-output device]를 클릭
- Screen Recording with Audio로 이름 변경

![screen recording with audio](https://github.com/gaba42/gaba42.github.io/assets/106816837/2e3282f4-f183-4cc8-82ad-07ab334f4deb)
- 전체 선택 해제
- 메인으로 사용하는 스피커(예. 노트북 내장 스피커, 블루투스 스피커, 헤드폰 등) 선택    
- Blackhole 16ch 선택
- Master Device도 제일 처음에 선택한 메인 스피커와 동일하도록 설정


## System Preference => Sound
![output](https://github.com/gaba42/gaba42.github.io/assets/106816837/7a8355a1-526f-481b-99eb-bcba016e1c95)
- Sound의 output 탭에서 먼저 만들어둔 [screen recording with audio] 선택

## Recording Option
![option](https://github.com/gaba42/gaba42.github.io/assets/106816837/9c6ead31-6588-4f0b-a516-d20f3e10a8cb)
- Shift + cmd + 5
- Option 드롭다운 메뉴
- Microphone 선택지 중에 미리 만들었던 [BlackHole Audio Input]을 선택

설정 끝.

## 주의사항
- 녹화 뒤에 스피커 설정을 원래대로 돌려두자. 안그러면 볼륨 조절이 되지 않는다.
