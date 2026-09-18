# Watch Log

드라마·영화 시청 기록 트래커. **저장소 이름은 `drama-tracker`, 앱 이름은 Watch Log** 입니다.

**▶ https://miel4ru-web.github.io/drama-tracker/**

빌드 도구도 의존성도 없는 정적 앱입니다. `index.html` 파일 하나가 전부라 브라우저로 직접 열어도
그대로 동작합니다.

## 기능

- 제목 / 타입(Drama·Movie·Anime·Documentary·Variety Show·Web Series) / 장르(14종) / 시청일 / 노트 기록
- 0–10 반별(half-star) 평점 — 클릭, 또는 방향키·Home·End 로 입력
- 타입별 그룹, 그룹마다 접기 + 정렬 기준·방향 선택
- 제목·장르·타입 검색
- Watched / Total / 평균 평점 요약
- 라이트·다크 테마 자동 전환
- localStorage 저장 + 선택적 GitHub Gist 동기화

## 데이터 저장

기본은 브라우저 **localStorage** 입니다. 이 경우 기록은 그 브라우저 안에만 있고, 사이트 데이터를
지우면 함께 사라집니다.

여러 기기에서 쓰려면 우측 상단 **Sync** 에서 GitHub 개인용 액세스 토큰을 넣습니다. 앱이
`drama-tracker-data.json` 이라는 비공개 gist 를 만들어 거기에 기록을 저장합니다.

### 토큰 주의사항

- 스코프는 **`gist` 하나만** 부여하고, **만료일(90일 정도)을 설정**하세요.
  [토큰 생성 링크](https://github.com/settings/tokens/new?scopes=gist&description=Watch+Log+sync)
- 토큰은 브라우저 localStorage 에만 저장되며 저장소에 커밋되지 않습니다.
- 다만 `miel4ru-web.github.io` 는 **origin 하나**입니다. 같은 계정의 다른 GitHub Pages 앱도
  같은 origin 에서 돌기 때문에, 그중 어느 앱의 스크립트든 여기 저장된 토큰을 읽을 수 있습니다.
  `repo` 같은 넓은 스코프의 토큰은 절대 넣지 마세요.

## 로컬 실행

```
git clone https://github.com/miel4ru-web/drama-tracker.git
```

`index.html` 을 브라우저로 열면 됩니다. 서버도 빌드도 필요 없습니다.

## 라이선스

[MIT](LICENSE)
