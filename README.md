# AI 대장 단톡방 · 토론실

클로드 대장, 연과장, 챗주임, 퍼대리, 제미니 팀원 다섯 명이 한 방에서 3라운드로 토론하고
최종 답변 초안과 매뉴얼(.md)을 만들어 주는 단일 HTML 웹앱입니다.

- 주소: https://gdhan77-cell.github.io/ai-debate-room/
- 대화창 아래 **📎 파일 첨부 (TXT·DOCX)** 버튼으로 원고·자료를 올리면 AI들이 그 내용까지 읽고 토론합니다.
- API 키는 브라우저(localStorage)에만 저장되고, 대화할 때 해당 회사 서버로만 전송됩니다.
  이 저장소에는 키·개인정보가 들어 있지 않습니다.
- 키 없이도 [▶ 데모 시연해 보기]로 전체 흐름을 체험할 수 있습니다.

## 파일 구성

- `index.html` — 앱 전체(HTML·CSS·JS 1장)

## 직접 고칠 때

`index.html` 하나만 수정해 커밋·푸시하면 몇 분 뒤 GitHub Pages에 반영됩니다.
TXT는 UTF-8을 먼저 읽고 실패하면 euc-kr로 다시 읽으며, DOCX는 브라우저 표준
`DecompressionStream('deflate-raw')`으로 `word/document.xml`만 풀어 읽습니다(외부 라이브러리 없음).
