# 📘 CS 스터디 운영 가이드

## 🎯 목적

- CS 지식 체계화
- 발표 & 면접 준비

---
## ⏰ 스터디 진행 시간

- 매주 수요일 18:30 ~

---
## 🧭 스터디 진행 방식

- 발표자의 **오른쪽 사람을 서기**로 지정한다. 서기는 클로바 노트를 활용해 스터디 내용을 기록한다.
- 발표자의 **왼쪽 사람부터 시계 방향으로** 발표자에게 **메인 질문**을 한다. 이후 순서가 다시 돌아오면 진행 시간을 확인하고 **서브 질문**을 진행한다.    
- 발표자를 제외한 모든 스터디원은 발표에 대한 **피드백을 노션**에 작성한다. (내용 및 태도 모두 가능)    
- 발표자가 대답한 후 **추가적으로 궁금한 사항이 있으면 꼬리 질문**을 할 수 있다. (꼬리 질문은 출제자가 아니어도 가능)
- 발표자의 내용에 대해 **추가 설명하고 싶은 스터디원은 자유롭게 발언권을 얻어 이야기**할 수 있다.
- 만약 발표자가 답변하지 못해 `pass`를 외칠 경우, **다른 스터디원이 대신 답변**할 수 있다.
- 모두 답변하지 못할 경우, **해당 개념을 정리하여 스터디 다음 날까지 제출**한다.

---
## 👥 스터디원

| [<img src="https://github.com/elitezer0.png" width="100px;" height="100px"/><br/><sub><b>EliteZer0</b></sub>](https://github.com/elitezer0)<br/>[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/elitezer0) | [<img src="https://github.com/QQQomputer.png" width="100px;" height="100px"/><br/><sub><b>QQQomputer</b></sub>](https://github.com/QQQomputer)<br/>[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/QQQomputer) | [<img src="https://github.com/baehoonbae.png" width="100px;" height="100px"/><br/><sub><b>baehoonbae</b></sub>](https://github.com/baehoonbae)<br/>[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/baehoonbae) | [<img src="https://github.com/ljh0401.png" width="100px;" height="100px"/><br/><sub><b>ljh0401</b></sub>](https://github.com/ljh0401)<br/>[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/ljh0401) | [<img src="https://github.com/rpeowiqu.png" width="100px;" height="100px"/><br/><sub><b>rpeowiqu</b></sub>](https://github.com/rpeowiqu)<br/>[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rpeowiqu) |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------- :|

---
## 🧾 컨벤션

### 📂 파일 명명 규칙

- 폴더와 파일 명은 모두 영문 소문자로 작성
- 공백은 **언더바(`_`)** 로 작성
- 파일명 형식: `이슈 라벨 명_깃허브 아이디`
	- 예: `database_elitezer0.md`

### 💬 커밋 컨벤션

| 작업 유형    | 커밋 메시지                     | 예시                             |
| -------- | -------------------------- | ------------------------------ |
| 파일 생성    | `docs: [카테고리] 한글 파일 명_작성자` | `docs: [database] 데이터베이스_정예영`  |
| 이미지 업로드  | `add: [카테고리] 커밋 메시지`       | `add: [database] 피터 첸 표기법 이미지` |
| 파일 내용 수정 | `update: [카테고리] 커밋 메시지`    | `update: [database] 누락된 내용 추가` |
| 파일 명 수정  | `rename: [카테고리] 커밋 메시지`    | `rename: [database] 이름 변경`     |
### 🔀 PR 가이드

- PR 제목: `[제출자] 학습 주제`
    - 예: `[정예영] HTTP & HTTPS`
- PR 시 해당 **학습 주제에 맞는 라벨**을 붙일 것
### 📄 PR 템플릿

```md
## 📚 학습 주제
ex) HTTP & HTTPS

---

## 📝 학습 내용 요약
> 핵심 키워드 위주 / 개념 요약 / 흐름 정리
>
> ex)
- HTTP란?
- HTTPS 동작 원리
- SSL Handshake 과정

---

## 🙋‍♀️ 질문 or 토론거리(선택)
> 개인적으로 헷갈렸거나 같이 얘기해보고 싶은 것들

ex)
- HTTPS 인증서 위조 가능성은 없나?
- TLS 1.3에서는 Handshake 방식이 어떻게 바뀌었는지?

---

## 🔗 참고 자료
> 링크, 블로그, 공식문서 등

- [Velog - HTTPS 쉽게 정리](https://velog.io/~~~)
- [MDN - HTTP 개념](https://developer.mozilla.org/~~~)

---

## ✅ 체크리스트
- [ ] 내용을 충분히 이해하고 정리했다.
- [ ] 다음 스터디에 발표가 가능하다.

```

## 📁 리포지토리 기본 폴더 구조

```bash
CS-Study/
├── database/
│   ├── database_elitezer0.md         # 해당 주제에 대한 md 정리
│   └── img/                          # 이미지 리소스 저장
│       └── erd_model.png
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── question-template.md
│   │   ├── retrospect-template.md
│   │   ├── study-run-template.md
│   │   └── study-submission-template.md
│   └── PULL_REQUEST_TEMPLATE.md
└── README.md

```
