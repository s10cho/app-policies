# app-policies

app-maker 로 만든 앱들의 **개인정보처리방침** 공개 페이지. GitHub Pages 로 배포한다.
앱 코드 저장소는 비공개로 두고, 스토어 심사에 필요한 공개 URL 만 여기서 낸다.

- 목록: https://s10cho.github.io/app-policies/
- 앱별: `https://s10cho.github.io/app-policies/<app>/privacy.html`

| 앱 | 방침 | 시행일 |
|---|---|---|
| TokenBar | [tokenbar/privacy.html](tokenbar/privacy.html) | 2026-09-30 |
| Voice Sprint | [voice-sprint/privacy.html](voice-sprint/privacy.html) | 2026-09-30 |

## 원칙

- **사실만 쓴다.** 앱이 실제로 하는 일(수집·저장 위치·전송·권한)과 한 글자도 어긋나지 않게. 기능이 바뀌면 배포 전에 방침부터 고친다
- **라이트 모드 고정, 시스템 글꼴, 외부 요청 0** — 방침 페이지 자체가 추적하지 않는다
- 한국어 + 영어 병기, 문의 이메일은 `csyull2287@gmail.com` 으로 통일
- 앱별 색은 페이지의 `--accent` 한 가지 (앱 아이콘 색)

## 새 앱 추가

```bash
mkdir <app> && cp _template/privacy.html <app>/privacy.html
# 1) {{APP_NAME}} {{EFFECTIVE_KO}} {{EFFECTIVE_EN}} {{ACCENT}} {{ACCENT_WASH}} 치환
# 2) 조항을 앱의 실제 동작에 맞게 수정 (권한 목록, 저장 위치, 외부 전송 여부)
# 3) <app>/icon.png (192px) 추가
# 4) index.html 목록과 이 README 표에 한 줄 추가
git add -A && git commit -m "<app>: 개인정보처리방침" && git push
```

push 하면 1~2분 뒤 Pages 에 반영된다. 스토어(App Store Connect, Play Console)에 위 URL 을 등록한다.

## 변경 이력은 git log 로 남긴다

방침을 고칠 때는 시행일을 바꾸고, 커밋 메시지에 무엇이 달라졌는지(예: "voice-sprint: 펼치기 기능 — OpenAI 전송 추가") 적는다.
