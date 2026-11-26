# arahann.github.io

[Jekyll](https://jekyllrb.com) + [Chirpy 테마](https://github.com/cotes2020/jekyll-theme-chirpy)로 만든 개인 블로그입니다.
주소: <https://arahann.github.io>

`main` 브랜치에 변경이 올라가면 GitHub Actions가 자동으로 사이트를 빌드하고 배포합니다 (보통 1~3분).

## 처음 한 번만 할 일

1. 저장소 **Settings > Pages** 로 이동
2. **Build and deployment > Source** 를 `GitHub Actions` 로 변경

이후로는 따로 할 일이 없습니다.

## 새 글 쓰는 법

1. `_posts` 폴더에 새 파일을 만듭니다.
   - 파일 이름 규칙: `YYYY-MM-DD-영문-제목.md` (예: `2026-11-27-my-first-post.md`)
   - 파일 이름의 영문 부분이 글 주소가 됩니다 (`/posts/my-first-post/`). 한글은 주소가 길어지므로 영문 권장.
2. 파일 맨 위에 아래 정보를 적습니다.

   ```yaml
   ---
   title: "글 제목"
   date: 2026-11-27 21:00:00 +0900
   categories: [일상]          # 대분류 하나 또는 [대분류, 소분류]
   tags: [메모]                # 여러 개 가능
   ---
   ```

3. 그 아래에 마크다운으로 본문을 씁니다.
4. 커밋하고 `main`에 올리면 몇 분 뒤 블로그에 나타납니다.
   GitHub 웹사이트에서 `_posts` 폴더 > **Add file > Create new file** 로 바로 써도 됩니다.

작성 예시 전체(코드 블록, 표, 이미지, 강조 상자)는 `_posts/2026-11-26-how-to-write-post.md` 를 참고하세요.

### 카테고리 예시

| 카테고리 | 용도 |
| --- | --- |
| 일상 | 일상 기록 |
| 개발 | 코드, 개발 메모 |
| 프롬프트 | AI 프롬프트 모음 |
| 주식 | 투자, 종목 분석 |

카테고리는 미리 만들 필요 없이, 글의 `categories`에 적으면 자동으로 생깁니다.

### 이미지 넣기

이미지는 `assets/img/posts/` 에 올리고 본문에서 이렇게 씁니다.

```markdown
![설명](/assets/img/posts/파일이름.png)
```

### 날짜 주의

`date`가 현재 시각보다 미래면 그 시각이 될 때까지 글이 보이지 않습니다. 시간대는 꼭 `+0900` 으로 적으세요.

## 블로그 설정 바꾸기

`_config.yml` 에서 바꿉니다.

| 항목 | 설명 | 현재 값 |
| --- | --- | --- |
| `title` | 블로그 제목 | `Steven의 블로그` (임시) |
| `tagline` | 제목 아래 한 줄 소개 | 임시 문구 |
| `description` | 검색엔진용 설명 | 임시 문구 |
| `avatar` | 사이드바 프로필 사진 경로 | 비어 있음 |
| `social.name` | 작성자 이름 | `Steven` |
| `theme_mode` | 비워두면 시스템 설정 따라감 + 다크모드 전환 버튼 | 비어 있음 |

자기소개 페이지는 `_tabs/about.md` 를 고치면 됩니다.

## giscus 댓글 켜기 (선택)

댓글은 현재 꺼져 있습니다. 켜려면:

1. 저장소 **Settings > General > Features** 에서 **Discussions** 체크
2. <https://github.com/apps/giscus> 에서 giscus 앱을 이 저장소에 설치
3. <https://giscus.app/ko> 에서 저장소 `arahann/arahann.github.io` 입력, 카테고리는 `Announcements` 선택
4. 화면에 나온 `data-repo-id`, `data-category-id` 값을 `_config.yml` 에 입력

   ```yaml
   comments:
     provider: giscus
     giscus:
       repo: arahann/arahann.github.io
       repo_id: 여기에_data-repo-id
       category: Announcements
       category_id: 여기에_data-category-id
   ```

## 내 컴퓨터에서 미리보기 (선택)

Ruby가 설치되어 있다면:

```bash
bundle install
bash tools/run.sh      # http://127.0.0.1:4000 에서 확인
```

## 폴더 구조

```text
_config.yml        블로그 전체 설정
_posts/            글 (여기에 .md 파일 추가)
_tabs/             사이드바 메뉴 페이지 (카테고리, 태그, 아카이브, 소개)
_data/contact.yml  사이드바 하단 아이콘 (GitHub, RSS)
assets/img/        이미지
.github/workflows/ 자동 배포 설정
```
