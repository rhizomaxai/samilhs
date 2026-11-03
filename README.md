# 학생 프로젝트 쇼케이스

학교별 데이터분석 수업에서 학생 팀이 만든 대시보드 웹앱을 모아 보여주는 정적 웹페이지입니다.
`index.html` 파일 하나로 동작하며 빌드 도구가 필요 없습니다.

## GitHub Pages 배포 방법

1. GitHub에서 새 저장소를 만듭니다. (예: `student-showcase`, Public)
2. **Add file → Upload files** 로 `index.html`, `README.md`를 올리고 **Commit changes**를 누릅니다.
3. 저장소의 **Settings → Pages**로 이동합니다.
4. **Source**: `Deploy from a branch`, **Branch**: `main` / `/(root)` 를 고르고 **Save**를 누릅니다.
5. 1~2분 뒤 페이지 위쪽에 나오는 주소로 접속합니다.
   `https://<깃허브아이디>.github.io/<저장소이름>/`

## 페이지 주소 구조

| 화면 | 주소 |
|---|---|
| 메인(참여 학교) | `.../` 또는 `.../#home` |
| 삼일고 · 미래유망 빅데이터분야 | `.../#samil-bigdata` |

프로그램 페이지 주소를 학생들에게 바로 공유할 수 있습니다.

## 내용 수정하기

`index.html` 아래쪽 `<script>` 안의 `DATA` 목록만 고치면 됩니다.

### 팀 추가·수정
```js
{ team: "F", members: ["홍길동","김철수"], url: "https://xxxx.streamlit.app/" },
```
새 팀 문자를 쓰면 `TEAM_COLORS`에도 색을 하나 추가합니다.
```js
const TEAM_COLORS = { A:"#1f4fd1", B:"#0f8a6a", C:"#c2410c", D:"#8a3fd1", E:"#b8860b", F:"#0e7490" };
```

### 학교 추가
`DATA` 배열에 학교 하나를 더 넣으면 메인 화면에 카드가 자동으로 생깁니다.
`slug`는 주소(`#slug`)로 쓰이므로 영문 소문자·숫자·하이픈만 사용합니다.
```js
{
  id: "newschool",
  school: "○○고등학교",
  programs: [{
    slug: "newschool-ai",
    name: "프로그램 이름",
    dept: "학과",
    grade: "1학년",
    platform: "Streamlit",
    projects: [
      { team: "A", members: ["학생1","학생2"], url: "https://..." }
    ]
  }]
}
```

## 참고

- Streamlit 무료 앱은 한동안 접속이 없으면 잠듭니다. 처음 열 때 깨우기 버튼을 누르고 30초~1분 기다리면 됩니다.
- 수정 후 GitHub에 다시 커밋하면 1~2분 안에 사이트에 반영됩니다.
