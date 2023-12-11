---
layout  : wiki
title   : 구글의 gemini 데모 영상은 진짜일까? 뻥일까?
summary : What the quack!
date    : 2023-12-11 11:40:00 +0900
updated : 2023-12-11 12:14:13 +0900
tag     : google gemini demo fake
resource: 9B/E2A7A3-25E4-4831-A040-D4AC54A55014
toc     : true
public  : true
parent  : [[/news]]
latex   : false
---
* TOC
{:toc}

한국 시간 기준으로 12월 7일에 구글에서 공개한 Gemini 데모 영상을 처음 접했었다. 특히나 계속 바뀌는 손의 모양을 보고 [가위바위보]를 하려는 것을 이해했다는 점에서 놀라웠다. (AI가 힘들어하는 부분이 맥락 파악이니까.)  

그런데 <u>구글</u>에서 게시한 블로그 포스트를 보고 의문이 들었던 것이,
> In this post, we’ll explore some of the prompting approaches we used in our Hands on with Gemini demo video.  
> 이 게시물에서는 Gemini 데모 동영상에서 사용한 몇 가지 프롬프트 방식에 대해 살펴봅니다.  

<br>

![what](https://github.com/gaba42/gaba42.github.io/assets/106816837/3b7825cd-1d87-4c24-86b7-9510d78b90fc)  
그렇다면 gemini는 영상을 보고 직접적으로 소통한게 아니라  텍스트(프롬프트)를 추가적으로 사용했다는 말인가? 

궁금해서 추가적으로 찾아보던 중 뭔가 석연치 않음을 느낀 사람들이 꽤 있다는 걸 알게되었고, 구글은 여전히 OpenAI 아래다는 내용의 블룸버그의 기사도 발견할 수 있었다.

## 데모 영상과 블로그 게시물의 차이
- 자동차 그리는 데모
    - 비디오: "디자인을 고려했을 때 이 중 어떤 것이 더 빠를까요?"
        - 자동차라고 알려주지도 않았는데?!
    - 블로그에 명시된 실제로 사용한 프롬프트: "다음 중 어느 차가 더 공기역학적인가요? 왼쪽에 있는 것과 오른쪽에 있는 것 중 어느 것이 더 공기역학적인가요? 구체적인 시각적 세부 사항을 사용하여 그 이유를 설명하세요."

- 그 외로 태양/지구/토성의 순서 데모에서도 실제 사용된 프롬프트와 다른 내용의 프롬프트를 데모 영상에서는 보여주고 있다.

## 블룸버그 기사
<img width="615" alt="Screen Shot 2023-12-11 at 11 56 19" src="https://github.com/gaba42/gaba42.github.io/assets/106816837/f9328e01-ca54-4687-8cba-5aeb5b116910">  
네, 실은 이미지 + 텍스트 였습니다.



구글도 AI 경쟁에 건재하다는 걸 보여주기 위함이였을까? 뭐가 되었든 간에 AI는 눈앞에 다가왔고 앞으로 5년 뒤의 사무직은 어떤 모습일지...... 분야 특성상 하나의 우세한 기업이 독점할 수 밖에 없다고 생각이 드는데 (지금의 경우에는 Open AI), 어찌보면 테크 분야의 기업들이 하고 있는 사업들은 국방사업과도 같지 않을까?


# 참고자료
- [Google's Gemini Looks Remarkable, But It's Still Behind OpenAI](https://www.bloomberg.com/opinion/articles/2023-12-07/google-s-gemini-ai-model-looks-remarkable-but-it-s-still-behind-openai-s-gpt-4)
- [Hands-on with Gemini: Interacting with Multimodal AI](https://www.youtube.com/watch?v=UIZAiXYceBI)
- [How it's Made: Interacting with Gemini through multimodal prompting](https://developers.googleblog.com/2023/12/how-its-made-gemini-multimodal-prompting.html)
