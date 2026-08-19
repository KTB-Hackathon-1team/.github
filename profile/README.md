<p align="center">
  <img width="210" alt="image" src="https://github.com/user-attachments/assets/17a2650b-dd70-4b1f-8580-4035e65df132" />

  <h1 align="center">코코아 (Cocoa)</h1>

</p>


> "괜찮아" 뒤에 숨은 아이의 진짜 마음, 코코아가 들려드립니다.
> 
![React](https://img.shields.io/badge/React-black?logo=react&logoColor=61DAFB)
![Nginx](https://img.shields.io/badge/Nginx-009639?logo=nginx&logoColor=white)
![SpringBoot](https://img.shields.io/badge/Spring%20Boot-6DB33F?logo=springboot&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?logo=jsonwebtokens&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI%20Realtime%20API-412991?logo=openai&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![AWSEC2](https://img.shields.io/badge/AWS%20EC2-FF9900?logo=amazonec2&logoColor=white)
![AWSRDS](https://img.shields.io/badge/AWS%20RDS-527FFF?logo=amazonrds&logoColor=white)


**해커톤 1팀** · 🔗 https://co-coa.kro.kr

---

## 📖 Description

코코아는 아이가 코코아(AI 캐릭터)와 자연스럽게 대화하며 오늘 있었던 일과 감정을 표현하고, 부모는 별도로 자신의 관찰과 걱정을 기록하는 서비스입니다. 

대화가 끝나면 AI가 이 둘을 함께 분석해, 리포트를 생성해 전달합니다.
 
코코아는 진단이나 치료를 하지 않습니다. 아이의 말을 잘 들어주고 감정을 언어로 바꾸도록 돕는 친구형 캐릭터입니다.

## ⭐ Main Feature 

### 육아 길잡이
 
- 아이와 코코아의 대화를 바탕으로 아이의 생각·감정·상황을 파악
- 이를 기반으로 아이의 정서에 맞는 육아 방법을 부모에게 제안
### 맞춤 유아 상담
 
- 8세 전후 아이도 부담 없이 대화할 수 있도록 쉬운 표현과 공감 중심의 대화 제공
- 아이가 자신의 감정과 생각을 스스로 표현하도록 자연스럽게 대화 유도

### 정보 분리 원칙
 
- 아이의 원문 대화는 부모 화면에 자동으로 공개되지 않고, 정리된 요약만 제공
- 부모가 입력한 관찰(메모)도 아이에게 노출하지 않으며, 코코아와의 대화 프롬프트에도 참고하지 않음
- 부모 메모는 세션 종료 후 아이가 표현한 내용과 비교하는 용도로만 사용
### 대화 안전 원칙
 
- 코코아는 질병명·원인·치료법을 단정하지 않고, 감정을 반영하며 신뢰할 수 있는 어른에게 말해보기를 부드럽게 제안
- 위험/긴급 표현 감지 시 일반 대화를 확장하지 않고, 보호자에게 알리도록 안내하는 고정 안전 메시지 표시 (프롬프트 + 서버 측 규칙 병행)



## 아키텍처 개요

- 아이는 마이크로 말하거나 텍스트로 입력할 수 있으며, 대화는 OpenAI Realtime API와 브라우저가 직접 통신해 실시간으로 처리됩니다.
- 백엔드는 세션·메시지·요약 저장, 인증, AI 서버와의 통신을 담당합니다.
- AI 서버(Python)는 대화 프롬프트 로직, 위험신호 감지, 요약 생성을 담당합니다.
- 세션이 끝나면 아이 대화 기록과 부모 메모를 함께 분석해, 아이용/부모용 요약을 한 번의 분석으로 생성합니다.
- 원본 음성은 저장하지 않으며, 텍스트 트랜스크립트만 기록으로 남습니다.

## 데이터 모델

`parents` · `children` · `parent_notes` · `sessions` · `messages` · `summaries`

- 부모 한 명이 여러 아이 프로필을 가질 수 있고, 아이 한 명은 여러 대화 세션을 가집니다.
- `sessions.parent_note_id`는 NOT NULL — 부모 메모 없이는 세션을 시작할 수 없어, 매 세션마다 부모-아이 관점을 비교할 수 있습니다.

### 👨‍👩‍👧‍👦 Developer

<table>
  <tr>
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/joonho7172"><img src="https://github.com/joonho7172.png" width="100px;" alt=""/></a>
      <br /><sub><b>martin.kim</b></sub>
      <br />풀스택
    </td>
    <td align="center">
      <a href="https://github.com/GitChan0456"><img src="https://github.com/GitChan0456.png" width="100px;" alt=""/></a>
      <br /><sub><b>river.so</b></sub>
      <br />풀스택
    </td>
    <td align="center">
      <a href="https://github.com/sim16065"><img src="https://github.com/sim16065.png" width="100px;" alt=""/></a>
      <br /><sub><b>mia.kang</b></sub>
      <br />클라우드
    </td>
    <td align="center">
      <a href="https://github.com/33jyu33"><img src="https://github.com/33jyu33.png" width="100px;" alt=""/></a>
      <br /><sub><b>janna.lee</b></sub>
      <br />클라우드
    </td>
    <td align="center">
      <a href="https://github.com/seheon99"><img src="https://github.com/seheon99.png" width="100px;" alt=""/></a>
      <br /><sub><b>ezra.yu</b></sub>
      <br />AI
    </td>
    <td align="center">
      <a href="https://github.com/sjnqkqh"><img src="https://github.com/sjnqkqh.png" width="100px;" alt=""/></a>
      <br /><sub><b>jung.yang</b></sub>
      <br />AI
    </td>
  </tr>
</table>