# 📌 Git & GitHub 사용 가이드

VS Code 환경에서 프로젝트를 GitHub 저장소와 연동하고, 코드를 관리/업로드하기 위한 명령어 레퍼런스 문서입니다.

---

## 🛠️ 1. 최초 프로젝트 연동 (Initial Setup)

프로젝트 폴더를 생성한 후 **처음으로 GitHub 저장소에 올릴 때** 사용하는 절차입니다.

```bash
# 1. 현재 폴더를 Git 저장소로 초기화
git init

# 2. 프로젝트 내 모든 변경 파일을 스테이지에 추가
git add .

# 3. 변경 사항 커밋 (첫 번째 버전 확정)
git commit -m "feat: Initial commit"

# 4. 기본 브랜치명을 main으로 변경
git branch -M main

# 5. 원격 저장소(GitHub) 주소 연결
git remote add origin https://github.com/사용자이름/저장소이름.git

# 6. GitHub 원격 저장소로 첫 푸시
git push -u origin main
```

> **Note**: `git push` 과정에서 인증 오류(`Authentication failed`)가 발생하는 경우, 브라우저 인증(Sign in with browser) 창을 통해 로그인 권한을 승인합니다.

---

## 🔄 2. 데일리 워크플로우 (Daily Push)

이후 코드를 수정하거나 새로운 실습 파일을 추가한 뒤 **GitHub에 변경 사항을 반영할 때** 사용하는 루틴입니다.

```bash
# 1. 수정된 모든 파일 스테이징
git add .

# 2. 커밋 메시지 작성 및 저장
git commit -m "docs: Update practice notes"

# 3. 원격 저장소로 업로드
git push
```

---

## 💡 주요 커밋 메시지 컨벤션 (Commit Convention)

| Prefix | Description |
| :--- | :--- |
| `feat:` | 새로운 기능이나 파일 추가 |
| `fix:` | 버그 또는 오타 수정 |
| `docs:` | 문서 수정 (`README.md` 등) |
| `refactor:` | 코드 리팩토링 |

---

## 📂 파일 삭제 및 동기화 처리

* **특정 파일 삭제 후 커밋 반영**:
  ```bash
  git add .
  git commit -m "remove: Delete unneeded file"
  git push
  ```
* **원격 저장소 주소 재설정**:
  ```bash
  git remote set-url origin [새로운_저장소_URL]
  ```
