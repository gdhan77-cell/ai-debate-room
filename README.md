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

### 사용법

⚙️ 설정 → **2. 무료 AI 자동 전환**에서 [이 앱에서 무료 AI 자동 전환 사용]을 켜고, 아래 [무료 AI 키 풀]에 키를 추가합니다.

## 무료 AI 자동 전환 (2026-11-25 추가)

- **Gemini · Groq · OpenRouter 무료 키**를 여러 개 넣어 두면 순서대로 호출하고, 한도(HTTP 429)·키 오류·서버 오류가 나면 **다음 무료 키로 자동 전환**합니다.
- 키 묶음은 브라우저 `localStorage`의 **`han_free_ai_pool_v1`** 한 곳에 저장되어, 같은 주소(gdhan77-cell.github.io)의 다른 앱과 `free-ai-hub`가 함께 씁니다.
- 옵션 **“무료 AI가 모두 한도 초과일 때만 내 클로드 키로 자동 보완”**(기본 켜짐)을 끄면 100% 무료 AI만 순환합니다.
- 어느 AI가 답했는지 메시지·보고서·상태 표시에 작게 나옵니다.
- 클로드 기본 모델을 **`claude-sonnet-5-5`** 로 올렸습니다. `claude-sonnet-4-5`는 2026-11-30 지원 종료이며, 모델을 찾지 못하면 `claude-sonnet-4-6` → `claude-sonnet-4-5` 순으로 자동 재시도합니다. (Sonnet 5.5는 `temperature`를 받지 않으므로 호출에서 뺐습니다.)
